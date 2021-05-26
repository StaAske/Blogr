<template>
    <section class="intro-sec">
            <div class="container">
                <h2 class="fade-in" id="test">Designed for the future</h2>

                <div class="intro-inner">
                        <div class="intro-inner-block fade-in">
                            <h3>Introducing an extensible editor</h3>
                            <p>Blogr features an exceedingly intuitive interface which lets you focus on one thing: creating content. 
                            The editor suppurts management of multiple blogs and allows easy manipulation of embeds such as images, videos, and Markdown. 
                            Extensibility with plugins and themes provide easy ways to add functionality or change the looks of a blog.</p>
                            
                            <h3>Robust content management</h3>
                            <p>Flexible content management enable users to easily move through posts. 
                            Increase the usability of your blog by adding  customized categories, sections, format, or flow. 
                            With this functionality, you're in full control.</p>
                        </div>
                        <!-- <div class="intro-inner-image">
                            <img class="" src="../assets/images/illustration-editor-desktop.svg">
                        </div> -->
                </div>
            </div>
    </section>
    <section class="art-infra">
        <div class="art-infra-bg-block">
            <div class="container">
                <div class="art-infra-inner-block">
                    <div class="art-img fade-in">
                        <img src="../assets/images/illustration-phones.svg" alt="">
                    </div>
                    <div class="art-text fade-in">
                        <h3>State of the Art Infrastructure</h3>
                        <p>With reliability and speed in mind, worldwide data centers provide the backbone for ultra-fast connectivity.
                        This ensures your site will load instantly, no matter where your reader are, keeping your site competitive.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: "IntroSection",
    data() {
        return {
            fadeInElements : []
        }
    },

    mounted() {
        this.fadeInElements = Array.from(document.getElementsByClassName('fade-in'))
        document.addEventListener('scroll', this.handleScroll)
        this.handleScroll()
    },

    methods: {
        handleScroll() {
            for(var i = 0; i < this.fadeInElements.length; i++) {
                var elem = this.fadeInElements[i]
                if(this.isElemVisible(elem)) {
                    elem.style.opacity = '1'
                    elem.style.transform ='scale(1)'
                    this.fadeInElements.splice(i, 1)
                }

            }
        },
        isElemVisible(el) {
            var rect = el.getBoundingClientRect()
            var elemTop = rect.top + 200
            var elemBottom = rect.bottom
            return elemTop < window.innerHeight && elemBottom >=0
        }
    }
    
}
</script>

<style lang="scss" scoped>
    
    .intro-sec {
        height: 100vh;
        position: relative;

        h2 {
            text-align: center;
        }

        .intro-inner {
                        
            .intro-inner-block{
                width: 50%;
                margin-top: 3.3em;
                padding-right: 1.2em;
            }
        }
    }
    .intro-sec::after {
        content: "";
        position: absolute;
        float: right;
        top: -110px;
        right: -280px;
        width: 60%;
        height: 120%;
        background-image: url(../assets/images/illustration-editor-desktop.svg);
        background-size: cover;
        background-repeat: no-repeat;
        
    }

    // State of the Art Infrastructure

    .art-infra {
        height: 100vh;
        display: flex;

        &-bg-block {
            height: 400px;
            background-color: $veryDarkGrayBlue;
            border-bottom-left-radius: 70px;
            border-top-right-radius: 70px;
            align-self: center;
            width: 100%;
            background-image: url('../assets/images/bg-pattern-circles.svg');
            background-repeat: no-repeat;
            background-position: -40% 80%;

        }
        &-inner-block {
            display: flex;
            .art-img {
                margin-top: -70px
            }
            .art-text > *{
                color: $white;
            }
            .art-text {
                margin-top: 75px;
                padding-left: 30px;
            }
        }
    }
</style>