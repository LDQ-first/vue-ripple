<template>
    <div class="show">
        <header>
            <h1>Vue Ripple Component</h1>
        </header>
        <article>
            <section class="section-first">
                <div class="ui">
                    <h2>Use</h2>
                    <p class="remind">
                        <img class="remind-img" src="../assets/icon/resume.svg">
                        <strong>You should restart vue after finishing install vue-useripple</strong>
                    </p>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeFirst.npm}}</code></pre>
                    <pre><code>{{codeFirst.js}}</code></pre>
                </div>
            </section>
            <section class="section-btn">
                <div class="ui">
                    <h2>Button Ripple</h2>
                    <ripple class="ripbtn" :isInline="isInline">
                        <button slot="pure" @click="showMoal">showModal</button>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeOne.js}}</code></pre>
                    <pre><code>{{codeOne.html}}</code></pre>
                    <pre><code>{{codeOne.css}}</code></pre>
                </div>
            </section>
            <section class="section-pan">
                <div class="ui">
                    <h2>Panel Ripple</h2>
                    <ripple class="ripPanel" children="one">
                        <div slot="children" class="panel children">
                            <header>
                                <h3>Panel</h3>
                            </header>
                            <div class="content">
                                <p>This is a Panel</p>
                            </div>
                            <button @click="showMoal" class="btn">showModal</button>
                        </div>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeTwo.js}}</code></pre>
                    <pre><code>{{codeTwo.html}}</code></pre>
                    <pre><code>{{codeTwo.css}}</code></pre>
                </div>
            </section>
            <section class="section-pan-btn">
                <div class="ui">
                    <h2>Panel&Button Ripple</h2>
                    <ripple class="ripPanel" children="one">
                        <div slot="children" class="panel children">
                            <header>
                                <h3>PanelBtn</h3>
                            </header>
                            <div class="content">
                                <p>This is a Panel&Button</p>
                            </div>
                            <footer>
                                <ripple class="ripbtn" :isInline="isInline">
                                    <button slot="pure" @click="showMoal">showModal</button>
                                </ripple>
                            </footer>
                        </div>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeThree.js}}</code></pre>
                    <pre><code>{{codeThree.html}}</code></pre>
                    <pre><code>{{codeThree.css}}</code></pre>
                </div>
            </section>
            <section class="section-param">
                <div class="ui">
                    <h2>Param Ripple</h2>
                    <ripple class="ripPanel" children="one">
                        <div slot="children" class="panel children">
                            <header>
                                <h3>Param</h3>
                            </header>
                            <div class="content">
                                <p>This is a Param</p>
                                <ul class="param-list">
                                    <li class="param-list-item">
                                        <strong>speed</strong>  
                                        <span class="des">type: String</span>
                                        <span class="des">default: 0.65s</span>
                                    </li>
                                    <li class="param-list-item">
                                        <strong>bg</strong>  
                                        <span class="des">type: String</span>
                                        <span class="des">default: #D8C9F8</span>
                                    </li>
                                    <li class="param-list-item">
                                        <strong>br</strong>  
                                        <span class="des">type: Boolean</span>
                                        <span class="des">default: false</span>
                                    </li>
                                </ul>
                                <ripple class="ripbtn" :isInline="isInline" speed="2">
                                    <button slot="pure">speed</button>
                                </ripple>
                                <ripple class="ripbtn" :isInline="isInline" bg="#2B72D6">
                                    <button slot="pure">background</button>
                                </ripple>
                                <ripple class="ripbtn" :isInline="isInline" :br="br">
                                    <button slot="pure" class="br">borderRadius</button>
                                </ripple>
                            </div>
                            <footer>
                                <ripple class="ripbtn" :isInline="isInline">
                                    <button slot="pure" @click="showMoal">showModal</button>
                                </ripple>
                            </footer>
                        </div>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeFour.js}}</code></pre>
                    <pre><code>{{codeFour.html}}</code></pre>
                    <pre><code>{{codeFour.css}}</code></pre>
                </div>
            </section>
        </article>
        <footer>
            <p>Copyright {{copyRightYear}} © by <a href="https://github.com/LDQ-first">LDQ-first</a> (◕ᴗ◕)</p>
            <p>
                demo source code in Github => 
                <a href="https://github.com/LDQ-first/vue-ripple-compoment" title="click me">
                    <img class="github-img" src="../assets/icon/github.svg" >
                </a>
            </p>
            <p>
                vue component source code in Github => 
                <a href="https://github.com/LDQ-first/vue-useripple" title="click me">
                    <img class="github-img" src="../assets/icon/github.svg" >
                </a>
            </p>
        </footer>
        <modal :mdShow="isShowModal" @close="closeModal">
            <p slot="message">
                {{modalMessage}}
            </p>
            <div slot="btnGroup" class="btnGroup">
                <button class="md-close" @click="closeModal">closeModal</button>
            </div>
        </modal>
    </div>
</template>

<script>
   /* const Ripple = resolve => require(['../components/ripple.vue'], resolve)*/
    const Modal = resolve => require(['../components/modal.vue'], resolve)
    
    export default {
        data () {
            return {
                codeFirst: {
                    npm: '',
                    js: ''
                },
                copyRightYear: '',
                isShowModal: false,
                modalMessage: 'This is a Modal',
                isInline: true,
                br: true,
                codeOne: {
                    html: '',
                    css: '',
                    js: ''
                },
                codeTwo: {
                    html: '',
                    css: '',
                    js: ''
                },
                codeThree: {
                    html: '',
                    css: '',
                    js: ''
                },
                codeFour: {
                    html: '',
                    css: '',
                    js: ''
                },
            }
        },
        components: {
            /*Ripple,*/
            Modal
        },
        created () {
            this.setCode()
            this.setYear()
        },
        methods: {
            showMoal () {
                this.isShowModal = true
            },
            closeModal () {
                this.isShowModal = false
            },
            setModalMessage (str) {
                this.modalMessage = str
            },
            setYear () {
                const year = new Date().getFullYear()
                console.log(year)
                if(year === 2017) {
                     this.copyRightYear = 2017
                } else {
                    this.copyRightYear = 2017 + ' - ' + year
                }
                
            },
            setCode () {
                this.codeFirst.npm =
`
/*-- npm --*/
npm install --save vue-useripple

`
                this.codeFirst.js = 
`
/*-- main.js --*/
import Vue from 'vue'
import VueRipple from 'vue-useripple'
Vue.use(VueRipple)
`
                this.codeOne.js =
    `
    /*-- js --*/
    export default { 
        data () {
            return {
                isInline: true
            }
        },
        methods: {
            showMoal () {
                this.isShowModal = true
            }
        }
    }
    `
                    this.codeOne.html = 
    ` 
    <!--html-->
    <ripple class="ripbtn" :isInline="isInline">
        <button slot="pure" @click="showMoal">showModal</button>
    </ripple>
    `
                    this.codeOne.css = 
    `
    /*--sass--*/
    .ripbtn {
        margin: 12px;
    }
    `
                    this.codeTwo.js =
    `
    /*-- js --*/
    export default { 
        methods: {
            showMoal () {
                this.isShowModal = true
            }
        }
    }
    `
                    this.codeTwo.html =
    `
    <!--html-->
    <div class="ui">
        <h2>Panel Ripple</h2>
        <ripple class="ripbtn" children="one">
            <div slot="children" class="panel children">
                <header>
                    <h3>Panel</h3>
                </header>
                <div class="content">
                    <p>This is a Panel</p>
                </div>
                <button @click="showMoal" class="ripbtn">showModal</button>
            </div>
        </ripple>
    </div>
    `
                    this.codeTwo.css =
    `
    /*--sass--*/
    @mixin panel {
        border: 2px solid #8BE388; 
        padding: 20px;
        background: #EEE;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        header {
            width: 100%;
            text-align: left;
        } 
        .content {
            margin: 20px 0;
        }
    }
    .section-pan {
        .rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
            @include panel
        }
        .btn {
            margin: 10px;
        }
    }
    `
                this.codeThree.js = 
    `
    /*-- js --*/
    export default { 
        data () {
            return {
                isInline: true
            }
        },
        methods: {
            showMoal () {
                this.isShowModal = true
            }
        }
    }

    `
                this.codeThree.html = 
    `
    <!--html-->
    <div class="ui">
        <h2>Panel&Button Ripple</h2>
        <ripple class="ripPanel" children="one">
            <div slot="children" class="panel children">
                <header>
                    <h3>Panel</h3>
                </header>
                <div class="content">
                    <p>This is a Panel</p>
                </div>
                <footer>
                    <ripple class="ripbtn" :isInline="isInline">
                        <button slot="pure" @click="showMoal">showModal</button>
                    </ripple>
                </footer>
            </div>
        </ripple>
    </div>
    `
                this.codeThree.css = 
    `
    /*--sass--*/
    @mixin panel {
        border: 2px solid #8BE388; 
        padding: 20px;
        background: #EEE;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        header {
            width: 100%;
            text-align: left;
        } 
        .content {
            margin: 20px 0;
        }
    }
    .section-pan-btn {
        .ripPanel.rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
             @include panel
        }
    }
    `
                this.codeFour.js = 
    `
    /*-- js --*/
    export default { 
        data () {
            return {
                isInline: true,
                br: true
            }
        },
        methods: {
            showMoal () {
                this.isShowModal = true
            }
        }
    }

    `
                this.codeFour.html = 
    `
    <!--html-->
    <div class="ui">
        <h2>Param Ripple</h2>
        <ripple class="ripPanel" children="one">
            <div slot="children" class="panel children">
                <header>
                    <h3>Param</h3>
                </header>
                <div class="content">
                    <p>This is a Param</p>
                    <ul class="param-list">
                        <li class="param-list-item">
                            <strong>speed</strong>  
                            <span class="des">type: String</span>
                            <span class="des">default: 0.65s</span>
                        </li>
                        <li class="param-list-item">
                            <strong>bg</strong>  
                            <span class="des">type: String</span>
                            <span class="des">default: #D8C9F8</span>
                        </li>
                        <li class="param-list-item">
                            <strong>br</strong>  
                            <span class="des">type: Boolean</span>
                            <span class="des">default: false</span>
                        </li>
                    </ul>
                    <ripple class="ripbtn" :isInline="isInline" speed="2">
                        <button slot="pure">speed</button>
                    </ripple>
                    <ripple class="ripbtn" :isInline="isInline" bg="#2B72D6">
                        <button slot="pure">background</button>
                    </ripple>
                    <ripple class="ripbtn" :isInline="isInline" :br="br">
                        <button slot="pure" class="br">borderRadius</button>
                    </ripple>
                </div>
                <footer>
                    <ripple class="ripbtn" :isInline="isInline">
                        <button slot="pure" @click="showMoal">showModal</button>
                    </ripple>
                </footer>
            </div>
        </ripple>
    </div>
    
    `
                this.codeFour.css = 
    `
    /*--sass--*/
    strong {
        margin: 0 20px;
    }
    .param-list {
        margin: 20px 0;
        .param-list-item {
            margin: 20px 0;
        }
    }
    @mixin panel {
        border: 2px solid #8BE388; 
        padding: 20px;
        background: #EEE;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        header {
            width: 100%;
            text-align: left;
        } 
        .content {
            margin: 20px 0;
        }
    }
    .section-param {
        .ripPanel.rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
             @include panel
        }
        .br {
            width: 88px;
            height: 88px;
        }
        .des {
            margin: 0 10px;
        }
    }
    `

                
                  
            }

        }
     }
</script>

<style lang="scss" scoped>
    h1, h2, h3, p{
        margin: 10px 0;
    }
    section, footer {
        margin: 50px 0;
    }
    strong {
        margin: 0 20px;
    }
    .remind {
        width: 80%;
        min-width: 800px;
        margin: 20px auto;
        border: 2px solid #8BE388; 
        padding: 20px 0;
        background: #EEE;
        display: flex;
        justify-content: center;
        align-items: center;
        .remind-img {
            margin: 0 20px;
        }
    } 
    .param-list {
        margin: 20px 0;
        .param-list-item {
            margin: 20px 0;
        }
    }
    .github-img {
        width: 30px;
        vertical-align: bottom;
        margin: 0 10px;
        animation: sway 2s ease-in-out infinite alternate;
        transform-origin: 50% 100%;
    }
    @keyframes sway {
        0% {
            transform: rotate(-35deg)
        }
        100% {
            transform: rotate(35deg)
        }
    }
    .ripbtn {
        margin: 12px;
    }
    .code {
        width: 80%;
        max-width: 768px;
        margin: 0 auto;
    }
    @mixin panel {
        border: 2px solid #8BE388; 
        padding: 20px;
        background: #EEE;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        header {
            width: 100%;
            text-align: left;
        } 
        .content {
            margin: 20px 0;
        }
    }
    .section-pan {
        .rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
            @include panel
        }
        .btn {
            margin: 10px;
        }
    }
    .section-pan-btn {
        .ripPanel.rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
             @include panel
        }
    }
    .section-param {
        .ripPanel.rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
             @include panel
        }
        .br {
            width: 88px;
            height: 88px;
        }
        .des {
            margin: 0 10px;
        }
    }
    

</style>