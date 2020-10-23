<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <transition name="router-anim" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<style>


    @import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";

    body {
        background: rgb(233, 233, 233);
        font-family:Arial, Helvetica, sans-serif;
    }
    html, body {
        height: calc(100% - 50px);
    }

    .page {
        background: #ffcc00;
        padding: 30px;
    }

    #nav {
        padding: 30px;
    }

    #app {
        background: #fff;
        width: 50%;
        border-radius: 10px;
        margin: 50px auto 0 auto;
        height: calc(60% - 50px);
        overflow: hidden;
    }

    .router-anim-enter-active {
        animation: coming 1s;
        animation-timing-function: cubic-bezier(.65,0,.32,1.55);
        opacity: 0;
    }

    .router-anim-leave-active {
        animation: going 1s;
        animation-timing-function: cubic-bezier(.8,-0.49,.36,1);
    }

    @keyframes going {
        from {
            transform: translateY(0);
        }
        to {
            transform: translateY(300px);
            opacity: 0;
        }
    }

    @keyframes coming {
        from {
            transform: translateY(300px);
            opacity: 0;
        }
        to {
            transform: translateY(0px);
            opacity: 1;
        }
    }


</style>
