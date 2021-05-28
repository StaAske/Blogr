<template>
    <section class="header-section">
      <div class="container">
        <header>
          <div class="header-logo-nav">
            <div class="logo">
                <img src="../assets/images/logo.svg" alt="logo">
            </div>
            <!-- <div class="nav"> -->
              <ul class="nav">
                <li @mouseover="fallDownMenu('product')" 
                    @mouseleave="productList = false"
                    class="li-arrow">Product<span></span>
                  <br>
                  <div v-if="productList" class="product-content">
                      <ul>
                          <li>Overview</li>
                          <li>Pricing</li>
                          <li>Marketplace</li>
                          <li>Features</li>
                          <li>Integrations</li>
                      </ul>
                  </div>
                </li>
                <li @mouseover="fallDownMenu('company')"
                    @mouseleave="companyList = false"
                    class="li-arrow">Company<span></span>
                  <br>
                  <div v-if="companyList" class="product-content">
                      <ul>
                          <li>About</li>
                          <li>Team</li>
                          <li>Blog</li>
                          <li>Careers</li>
                      </ul>
                  </div>
                </li>
                <li @mouseover="fallDownMenu('connect')"
                    @mouseleave="connectList = false"
                    class="li-arrow">Connect<span></span>
                  <br>
                  <div v-if="connectList" class="product-content">
                      <ul>
                          <li>Contact</li>
                          <li>Newsletter</li>
                          <li>LinkedIn</li>
                      </ul>
                  </div>
                </li>
              </ul>
              <!-- <router-link to="/">Home</router-link> -->
              <!-- <router-link to="/about">About</router-link> -->
            <!-- </div> -->
          </div>
          <!-- <div class="reg-in"> -->
            <ul class="reg-in">
              <li class="login">Login</li>
              <li class="sign-up">Sign Up</li>
            </ul>
          <!-- </div> -->
        </header>

        <div class="head-content">
          <h1>A modern publishing platform</h1>
          <h4>Grow your audience and build your online brand</h4>
          <ul>
            <a href="#" class="freeStart"><li>Start for free</li></a>
            <a href="#" class="learnMore"><li>Learn More</li></a>
          </ul>
        </div>
      </div>
    </section>
</template>

<script>
export default {
    name: 'HeaderSection',
    components: {

    },
    data() {
      return {
        productList: false,
        companyList: false,
        connectList: false,
      }
    },
    methods: {
      fallDownMenu(el) {
        if(el === 'product') {
          this.productList = true
        } else if (el === 'company') {
          this.companyList = true
        } else if (el === 'connect') {
          this.connectList = true
        }
      }
    }

}
</script>

<style lang="scss">
    section.header-section {
        height: 600px;
        color: $white;
        background: rgb(255,143,112);
        background-image: url("../assets/images/bg-pattern-intro.svg");
        background-repeat: no-repeat;
        background-size: auto auto;
        background-position: 40% 50%;
        border-bottom-left-radius: 70px;
        margin-bottom: 100px;


        header {
          display: flex;
          justify-content: space-between;
          height: 150px;

          .reg-in {
            float: right;
            
            .login {
              @include headBtns($bgColorIs);
              font-family: $btnFont;
            }

            .sign-up {
              background-color: $white;
              color: $lightRed;
              transition-property: background-color;
              font-family: $btnFont;
              @include headBtns($white);
            }
            
          }
        }

        .header-logo-nav {
            display: flex;
            align-items: center;



            li.li-arrow {
                padding: 8px;
                margin-left: 45px;
                position: relative;


                ul {
                    display: block;
                    position: absolute;
                    color: $veryDarkBlue;
                    background-color: $white;
                    padding: 25px 25px;
                    border-radius: 8px;
                    line-height: 2;
                    z-index: 2;
                    margin-left: -20px;
                    margin-top: 7px;

                    li {
                        margin: 0;
                        font-weight: 300;
                    }
                    li:hover {
                      font-weight: 600;
                    }
                }
                
                span {
                    display: inline-block;
                    width: 10px;
                    height: 7px;
                    background-image: url("../assets/images/icon-arrow-light.svg");
                    background-repeat: no-repeat;
                    transition: all 0.4s ease;
                    margin-left: 5px;
                }

            }
            .li-arrow:hover {
                text-decoration: underline;
                span {
                    transform: rotate(180deg);
                }
            }
        }

      .head-content {
          text-align: center;

        h1 {
          font-size: 4rem;
          margin-top: .7em;
          margin-bottom: 0.2em;
        }
        h4 {
          font-size: 1.5rem;
          font-weight: 300;
          margin-bottom: 1.7em;
        }
        ul {
          display: flex;
          justify-content: center;
        }
        .freeStart {
          background-color: $white;
          color: $veryLightRed;
          margin-right: 30px;
          @include headBtns($white);
        }
        .learnMore {
          // transition-duration: 1s;
          color: $white;
          border: 1px solid $white;
          @include headBtns($veryLightRed);
        }
      }
    }
</style>