<template>
    <div class="slide-wrapper" @keydown.space.prevent="togglePlay">
        <h1>Audio slowdown</h1>
        <row>
            Speed x{{speed}}
            <slider v-model="speedSlider" show-tip="never"></slider>
        </row>
        <row @mousedown.native="togglePlay" @mouseup.native="togglePlay">
            Playing at {{playPosition | formatTime}}
            <slider :value="playSliderPosition" show-tip="never" @on-input="changePlayPosition"></slider>
        </row>
        <row v-if="loop">
            <slider range :value="loopRange" @on-input="changeLoopRange" show-tip="never"></slider>
        </row>
        <row class="buttons">
            <i-button @click="$refs.fileLoader.click()">Choose file</i-button>
            <input type="file" style="display: none;" ref="fileLoader" @change="readFile"/>
            <i-button :disabled="!audio" @click="togglePlay">{{playing ? 'Pause' : 'Play'}}</i-button>
        </row>
        <row style="margin-top: 20px">
            <h4>Settings:</h4>
            <p>Loop: <i-switch v-model="loop" :disabled="!audio"></i-switch></p>
        </row>



    </div>
</template>

<script>
    export default {
        data(){
            return {
                speedSlider: 50,
                playPosition: 0,
                playSliderPosition: 0,
                fileName: '',
                audio: null,
                loading: false,
                playing: false,
                playFrom: 0,
                playTo: Infinity,
                loop: false,
                loopRange: [0, 100]
            }
        },
        computed: {
            speed(){
                return (this.speedSlider + 50) / 100;
            },
        },
        watch: {
            speedSlider(){
                this.audio.playbackRate = this.speed;
            },
            playing(playing){
                const checkState = () => {
                    if (!this.playing || !this.audio) return;
                    this.playPosition = this.audio.currentTime.toFixed(2);
                    setTimeout(checkState, 250);
                };
                if (playing) this.audio.play();
                else this.audio.pause();
                checkState();
            },
            playPosition(){
                if (this.playing && this.audio.currentTime >= this.playTo) {
                    this.audio.currentTime = this.playFrom;
                    this.audio.play();
                }
                this.updatePlaySliderPosition();
            },
            loop(){
                this.changeLoopRange([0, 100]);
            }
        },
        methods: {
            readFile(e){
                const reader = new FileReader();
                const input = e.target;
                reader.readAsDataURL(input.files[0]);
                this.loading = true;
                reader.onload = e => {
                    const fileName = input.value.match(/[^/\\]+$/);
                    this.fileName = fileName;
                    this.audio = new Audio(e.target.result);
                    this.loopRange = [0, 100];
                    this.loading = false;
                };
            },
            togglePlay(){
                if (!this.audio) return;
                this.playing = !this.playing;
            },
            updatePlaySliderPosition(){
                if (!this.audio) this.playSliderPosition = 0;
                this.playSliderPosition = this.playPosition * 100 / this.audio.duration;
            },
            changePlayPosition(val){
                if (this.playing || !this.audio) return;
                this.audio.currentTime = val * this.audio.duration / 100;
            },
            changeLoopRange([from, to]){
                this.playFrom = from * this.audio.duration / 100;
                this.playTo = to * this.audio.duration / 100;
            }
        },
        filters: {
            formatTime(secs){
                return [secs / 60, secs % 60].map(Math.floor).map(s => (s < 10) ? '0' + s : s).join(':')
            }
        }
    }
</script>

<style scoped>
    .buttons > *{
        margin-right: 10px;
    }
</style>
