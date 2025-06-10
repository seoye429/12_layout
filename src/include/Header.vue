<template>

<v-app-bar app>
    <v-toolbar-title>Vuetify reference</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn text :to="'/home'" >Home</v-btn>

    <v-menu offset-y>
        <template #activator="{props}">
            <v-btn v-bind="props" text>
                Vue Html용
                <v-icon end>mdi-menu-down</v-icon>
            </v-btn>
        </template>
        <v-list>
            <v-list-item
            v-for="(vues,index) in vuesItems" 
            :key="index"
            @click="navigate(vues.link)"
            >
                <v-list-item-title>{{ vues.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>

    <v-menu offset-y>
        <template #activator="{props}">
            <v-btn v-bind="props" text>
                Vue 설치용
                <v-icon end>mdi-menu-down</v-icon>
            </v-btn>
        </template>
        <v-list>
            <v-list-item
            v-for="(vues,index) in vuesItems" 
            :key="index"
            @click="navigate(vues.link)"
            >
                <v-list-item-title>{{ vues.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>

    <v-menu offset-y>
        <template #activator="{props}">
            <v-btn v-bind="props" text>
                Vuetify
                <v-icon end>mdi-menu-down</v-icon>
            </v-btn>
        </template>
        <v-list>
            <v-list-item
            v-for="(item,index) in menuItems" 
            :key="index"
            @click="navigate(item.link)"
            >
                <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>

     <v-menu offset-y>
        <template #activator="{props}">
            <v-btn v-bind="props" text>
                Nav
                <v-icon end>mdi-menu-down</v-icon>
            </v-btn>
        </template>
        <v-list>
            <v-list-item
            v-for="(nav,index) in navItems" 
            :key="index"
            @click="navigate(nav.link)"
            >
                <v-list-item-title>{{ nav.title }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-menu>


    
</v-app-bar>

<v-main>
    <router-view></router-view>
</v-main>

</template>

<script setup>
import {ref} from 'vue';

const vuesItems=ref([
    {title:'뷰디렉티브Dir',link:'/dir'},
    {title:'이벤트',link:'/events'},
    {title:'Vue Methods함수',link:'/met'},
    {title:'계산된속성Computed Properties',link:'/comp'},
    {title:'v-model',link:'/vmodel'},
    {title:'워처스',link:'/watchers'},
])

const menuItems=ref([
    {title:'빵부스러기bread',link:'/bread'},
    {title:'Tabs',link:'/tabs'},
    {title:'button',link:'/button'},
    {title:'Flaoting Btn',link:'/fbutton'},
    {title:'Bottom navi',link:'/bottom1'},
    {title:'hello',link:'hello'},
    {title:'tooltip툴팁',link:'tooltip'},
    {title:'footers',link:''},
    {title:'페이지네이션',link:'page'},
])

const navItems=ref([
    {title:'nav1',link:'/nav1'},
    {title:'nav2',link:'/nav2'},
    {title:'nav3',link:'/nav3'},
    {title:'nav4',link:'/nav4'},
    {title:'nav5',link:'/nav5'},
])





//add
import { useRouter } from 'vue-router'

const router = useRouter()

function navigate(link) {
  router.push(link)
}
</script>
