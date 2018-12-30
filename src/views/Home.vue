<template>
    <v-app light >
        <v-content>
            <section>
                <v-parallax :src="banner"  id="page" height="600">
                    <v-toolbar flat class="white--text transparent">
                        <v-toolbar-side-icon class="white--text" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
                        <v-toolbar-title v-text="title"></v-toolbar-title>
                        <v-spacer></v-spacer>
                        <v-toolbar-items class="hidden-sm-and-down">
                            <v-btn class="white--text" flat >Home</v-btn>
                            <v-btn class="white--text" flat href="#features" @click.stop="drawer=false">Features</v-btn>
                            <v-btn class="white--text" flat href="#download" @click.stop="drawer=false">Download</v-btn>
                            <v-btn class="white--text" flat href="https://github.com/elliottzheng/CopyTranslator/wiki/Usage-%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97" @click.stop="drawer=false">User Manual</v-btn>
                        </v-toolbar-items>
                    </v-toolbar>
                    <v-layout
                            column
                            align-center
                            justify-center
                            class="white--text"
                    >
                        <img src="logo.ico" alt="Vuetify.js" height="200">
                        <h1 class="white--text mb-2 display-1 text-xs-center">CopyTranslator</h1>
                        <div class="subheading mb-2 text-xs-center">Foreign language assisted reading and translation solution</div>
                        <div class="subheading mb-3 text-xs-center">Latest: {{version}}</div>
                        <v-btn
                                round
                                class="blue lighten-2 mt-5"
                                large
                                dark
                                href="#download"
                        >
                            Download
                        </v-btn>
                    </v-layout>
                </v-parallax>
            </section>

            <section id="features">
                <v-layout
                        column
                        wrap
                        class="my-5"
                        align-center
                >
                    <v-flex xs12 sm4 class="my-3">
                        <div class="text-xs-center">
                            <h2 class="headline">A fantastic way of document translation</h2>
                            <span class="subheading">
                Copy and Translate with CopyTranslator
              </span>
                        </div>
                    </v-flex>
                    <v-flex xs12>
                        <v-container grid-list-xl>
                            <v-layout row wrap align-center>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa-magic</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline">Fluency Translation</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Solving the problem caused by extra sentence breaks and line breaks.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa-clipboard</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Clipboard Monitor</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Just copy the text to the clipboard, and wait to view the translation results in the next second, enjoy the WYSIWYG pleasure.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>

                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa fa-sync</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Intelligent Mutual Translation</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Intelligently translate according to the source language and target language,
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa fa-copy</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline">Incremental Copy</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Append the copied text to the source other than replace it, especially useful when the paragraph is separated in different page.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa fa-hand-pointer</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Press Copy</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Just select the text, and hover the mouse over the selected text, after long press and release, it can be copied.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large class="blue--text text--lighten-2">fa fa-book</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Smart Dictionary</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Sentences with words less than 3 will be view as phrase or word, you will see a more detailed explanations in Focus Mode.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large @click.stop="toGithub" class="blue--text text--lighten-2">fa fa-wrench</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Powerful Automation</div>
                                        </v-card-title>
                                        <v-card-text>
                                            Many automated customization options are available.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                                <v-flex xs12 md3>
                                    <v-card class="elevation-0 transparent">
                                        <v-card-text class="text-xs-center">
                                            <v-icon x-large @click.stop="toGithub" class="blue--text text--lighten-2">fab fa-github</v-icon>
                                        </v-card-text>
                                        <v-card-title primary-title class="layout justify-center">
                                            <div class="headline text-xs-center">Completely Open Sourced</div>
                                        </v-card-title>
                                        <v-card-text>
                                            The code is licensed under Mozilla Public License 2.0, and it's available on Github.
                                        </v-card-text>
                                    </v-card>
                                </v-flex>
                            </v-layout>
                        </v-container>
                    </v-flex>
                </v-layout>
            </section>

            <section id="download" >
                <v-parallax :src="banner" height="380">
                    <v-layout column align-center justify-center>
                        <div class="headline white--text mb-3 text-xs-center">Paper reading has never been easier</div>
                        <em>Kick-start your journey now</em>
                        <v-btn
                                class="blue lighten-2 mt-5"
                                dark
                                large
                                round
                                href="https://github.com/elliottzheng/CopyTranslator/wiki/Downloads-%E4%B8%8B%E8%BD%BD%E4%B8%8E%E5%AE%89%E8%A3%85"
                        > 
                            Download from Github
                        </v-btn>
                    </v-layout>
                </v-parallax>
            </section>
            <section>
                <v-container grid-list-xl>
                    <v-layout row wrap justify-center class="my-5">
                        <v-flex xs12 sm4>
                            <v-card class="elevation-0 transparent">
                                <v-card-title primary-title class="layout justify-center">
                                    <div class="headline">About author</div>
                                </v-card-title>
                                <v-card-text>
                                    I'm Elliott Zheng, my research interests lie in computer vision and deep learning. Specifically, I am interested in 3D  computer vision and graph learning. Also a amateur front-end developer.
                                </v-card-text>
                            </v-card>
                        </v-flex>
                        <v-flex xs12 sm4 offset-sm1>
                            <v-card class="elevation-0 transparent">
                                <v-card-title primary-title class="layout justify-center">
                                    <div class="headline">Contact me</div>
                                </v-card-title>
                                <v-list class="transparent">
                                    <v-list-tile>
                                        <v-list-tile-action>
                                            <v-icon class="blue--text text--lighten-2">fab fa-github</v-icon>
                                        </v-list-tile-action>
                                        <v-list-tile-content>
                                            <v-list-tile-title><a href="https://github.com/elliottzheng">https://github.com/elliottzheng</a></v-list-tile-title>
                                        </v-list-tile-content>
                                    </v-list-tile>
                                    <v-list-tile>
                                        <v-list-tile-action>
                                            <v-icon class="blue--text text--lighten-2">fa-envelope</v-icon>
                                        </v-list-tile-action>
                                        <v-list-tile-content>
                                            <v-list-tile-title><a href="mailto:CopyTranslator@hypercube.top">CopyTranslator@hypercube.top</a></v-list-tile-title>
                                        </v-list-tile-content>
                                    </v-list-tile>
                                </v-list>
                            </v-card>
                        </v-flex>
                    </v-layout>
                </v-container>
            </section>
        </v-content>
        <v-navigation-drawer
                v-model="drawer"
                temporary
                width = "200"
                id = "drawer"
                class='mt-5 transparent'
                clipped
                app
        >
            <v-btn class="white--text" flat >Home</v-btn>
            <v-btn class="white--text" flat href="#features" @click.stop="drawer=false">Features</v-btn>
            <v-btn class="white--text" flat href="#download" @click.stop="drawer=false">Download</v-btn>
            <v-btn class="white--text" flat href="https://github.com/elliottzheng/CopyTranslator/wiki/Usage-%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97" @click.stop="drawer=false">User Manual</v-btn>
        </v-navigation-drawer>
        <v-footer class="blue darken-2">
            <v-layout row wrap align-center>
                <v-flex xs12>
                    <div class="white--text ml-3">
                        Made by <a class="white--text" href="https://vuetifyjs.com" target="_blank">Vuetify</a>
                        and <a class="white--text" href="https://github.com/elliottzheng">Elliott Zheng</a>

                    </div>
                    <div><a class="white--text" href="https://www.freepik.com/free-vector/technology-background-with-gradient-colors_2364158.htm">Designed by Freepik</a></div>
                </v-flex>
            </v-layout>
        </v-footer>
    </v-app>
</template>

<script>
//Photo by Steve Johnson from Pexels
export default {
  data: function() {
    return {
      title: "CopyTranslator",
      banner1: require("../assets/bg.png"),
      banner: require("../assets/background.jpg"),
      drawer: false,
      version: "v0.0.7 RC1"
    };
  },
  methods: {
    toGithub: function() {
      window.location("https://github.com/elliottzheng/CopyTranslator");
    }
  }
};
</script>
