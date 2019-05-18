<template>
  <ion-app>
    <ion-toolbar color="gray">
        <ion-buttons slot="secondary">
            <ion-button>
                F&R
            </ion-button>
        </ion-buttons>
        <ion-title>
            Food & Recipes
        </ion-title>
    </ion-toolbar>

    <!-- <div id="nav">
        <router-link to="/">Main</router-link> 
       <router-link to="/about">About</router-link>
    </div> -->

    <ion-content color="light">
        <router-view/>
    </ion-content>
  </ion-app>
</template>

