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
                </div>
            </div>
            <div class="first-intro-image">
                <img class="" src="../assets/images/illustration-editor-desktop.svg">
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
    <section class="art-infra-2">
        <div class="art-img">
            <img src="../assets/images/illustration-laptop-desktop.svg" alt="">
        </div>
        <div class="container">
            <div class="inner-block">
                <div class="art-text-1 fade-in">
                    <h3>Free, open, simple</h3>
                    <p>Blogr is a free and open source application backed by a large community of helpful developers.
                    It supports features suck as code syntax highlighting, RSS feeds, social media integration, third-party commenting tools, and works seamlessly with Google Analytics. 
                    The architecture is clear and is relatively easy to learn.
                    </p>
                    <h3>Powerful tooling</h3>
                    <p>Batteries included. We built a simple and straightforward CLI tool that makes customization and deployment a breeze, 
                    but capable of producting even the most complicated sites.</p>
                </div>
            </div>
        </div>
    </section>
    <footer>
        <div class="container">
            <div class="inner-footer-block">
                <div class="footer-logo">
                    <img src="../assets/images/logo.svg" alt="">
                </div>
                <ul class="product">
                    <li>Product</li>
                    <li>Overview</li>
                    <li>Pricing</li>
                    <li>Marketplace</li>
                    <li>Features</li>
                    <li>Integrations</li>
                </ul>

                <ul class="company">
                    <li>Company</li>
                    <li>About</li>
                    <li>Team</li>
                    <li>Blog</li>
                    <li>Careers</li>
                </ul>

                <ul>
                    <li>Connect</li>
                    <li>Contact</li>
                    <li>Newsletter</li>
                    <li>LinkedIn</li>
                </ul>
            </div>
        </div>
    </footer>
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
        height: 820px;
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
    .first-intro-image {
        display: inline-block;
        position: absolute;
        right: -275px;
        top: -70px;
        z-index: -1;
    }

    // State of the Art Infrastructure

    .art-infra {
        height: 600px;
        margin-top: 100px;

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
    // Addintional info
    .art-infra-2 {
        height: 800px;
        .art-img {
            display: inline-block;
            position: absolute;
            left: -275px;
            z-index: -1;
        }
        .inner-block {
            .art-text-1 {
                float: right;
                width: 50%;
                margin-top: 150px;
            }
        }
    }
    // Footer
    footer {
        background-color: $veryDarkBlackBlue;
        border-top-right-radius: 70px;
        padding-top: 90px;
        margin-top: 100px;
        .inner-footer-block {
            display: flex;
            justify-content: space-around;
            height: 340px;

            ul {
                display: block;
                color: $white;

                li {
                    font-weight: 400;
                    padding: .7em;
                }
                li:hover {
                    text-decoration: underline;
                }
                li:nth-of-type(1) {
                    padding-bottom: 1em;
                    font-weight: 700;
                    text-decoration: none;
                    cursor: auto;
                    
                }
            }
        }
        
    }
</style>