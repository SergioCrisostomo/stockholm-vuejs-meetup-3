<template>
    <div id="app" @keyDown.left.right="navigate">
        <Layout>
            <Content>
                <component :is="currentSlide"></component>
            </Content>
            <Footer>{{slide + 1}}/{{slides.length}}</Footer>
        </Layout>
    </div>
</template>

<script>
    import slides from './Slides/index';

    export default {
        data() {
            return {
                slides: slides,
                slide: 0,
            };
        },
        computed: {
            currentSlide() {
                return this.slides[this.slide];
            }
        },
        methods: {
            navigate(increment) {
                this.slide = (this.slide + increment + this.slides.length) % this.slides.length;
            }
        },
        mounted() {
            window.addEventListener('keydown', ({keyCode}) => {
                if (keyCode !== 37 && keyCode !== 39) return;
                const increment = keyCode === 37 ? -1 : 1;
                this.navigate(increment);
            });
        },
    }
</script>

<style>
    html, body {
        height: 100%;
        margin: 0;
        padding: 0;
    }

    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin: 0;
        height: 100%;
        font-size: 16px;
    }

    .ivu-layout {
        height: 100%;
    }

    .ivu-layout-content {
        padding-top: 40px;
    }

    h1, h2, h3 {
        color: #42b883
    }

    p {
        color: white;
    }

    /* SLIDES */
    .slide-wrapper {
        padding: 0 50px;
        text-align: left;
    }

    .slide-wrapper h1 {
        padding-bottom: 20px;
    }

    .slide-wrapper p {
        color: black;
    }

    .ivu-slider {
        font-size: 12px;
    }

</style>
