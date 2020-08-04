<template>
    <div class="mx-auto overflow-hidden">
        <nav>
            <v-toolbar dense height="58" color="#00695C" dark  prominent>
                <div>
                    <v-btn icon>
                        <v-icon @click.stop="drawer = !drawer">menu</v-icon>
                    </v-btn>
                </div>

                <v-toolbar-title><h3 class="textcenter">Radowan Redoy</h3></v-toolbar-title>

                <v-spacer></v-spacer>

                <v-btn icon>
                    <v-icon>mdi-magnify</v-icon>
                </v-btn>

                <v-btn icon>
                    <v-icon><router-link to="./components/about.vue"></router-link></v-icon>
                </v-btn>

                <v-btn icon>
                    <v-icon>mdi-heart</v-icon>
                </v-btn>

                <v-btn icon>
                    <v-icon>mdi-dots-vertical</v-icon>
                </v-btn>
            </v-toolbar>
        </nav>
        <v-navigation-drawer
                v-model="drawer"
                width="220px"
                absolute
                bottom
                temporary
                color="#DCEDC8"
        >
            <div class="profilediv">
                <div class="imgdiv">
                    <v-img class="img" :aspect-ratio="1/1" src="https://cdn.vuetifyjs.com/images/parallax/material.jpg">
                    </v-img>
                </div>

                <v-list-item>
                    <v-list-item-content>
                        <v-list-item-title class="title">
                            <h2>Radowan Redoy</h2>
                        </v-list-item-title>
                        <v-list-item-subtitle>
                            <h5>Institute Of Information Technology,</h5>
                        </v-list-item-subtitle>
                        <v-list-item-subtitle>
                            <h5>University Of Dhaka</h5>
                        </v-list-item-subtitle>
                    </v-list-item-content>
                </v-list-item>
            </div>

            <v-divider></v-divider>
            <v-list
                    nav
                    dense
            >
                <v-list-item-group
                        v-model="group"
                        active-class="deep-purple--text text--accent-4"
                >
                    <v-list-item>
                        <v-list-item-icon>
                            <v-icon>mdi-view-dashboard</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title class="textpadding">Home</v-list-item-title>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-icon>
                            <v-icon>mdi-help-box</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title class="textpadding">About</v-list-item-title>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-icon>
                            <v-icon>search</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title class="textpadding">Search</v-list-item-title>
                    </v-list-item>

                    <v-list-item>
                        <v-list-item-icon>
                            <v-icon>person</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title class="textpadding">Contact</v-list-item-title>
                    </v-list-item>
                </v-list-item-group>
            </v-list>

            <template v-slot:append>
                <div class="divlogoutbutton">
                    <v-btn block>Logout</v-btn>
                </div>
            </template>
        </v-navigation-drawer>

        <v-card-text>
            The navigation drawer will appear from the bottom on smaller size screens.
        </v-card-text>
    </div>
</template>

<script>
    export default {
        data: () => ({
            drawer: false,
            group: null,
        }),

        watch: {
            group () {
                this.drawer = false
            },
        },
    }
</script>

<style scoped>
    .textcenter{
        text-align: center;
    }
    .textpadding{
        padding-left: 18px;
    }
    .img{
        border-radius: 50%;
        display: block;
    }
    .imgdiv{
        width: 200px;
        height: 170px;
        padding-left: 37px;
        padding-right: 30px;
        padding-top: 30px;
        padding-bottom: 18px;
    }
    .profilediv{
        background-color: #AED581;
    }
    .divlogoutbutton{
        elevation: 10rad;
        padding: 18px;
    }
</style>