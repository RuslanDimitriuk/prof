<template>
    <div>
      <header-custom/>
        <router-view/>
        <footer-custom/>
    </div>
</template>
<script>
    import HeaderCustom from './components/HeaderCustom';
    import FooterCustom from "./components/FooterCustom";

    export default {
        name: 'App',
        components: {
            FooterCustom,
            HeaderCustom
        },
        data() {
            return {}
        },
        computed: {},
        methods: {},
    }
</script>
<style>
    @import './../node_modules/reset-css/reset.css';
    body{
        font-family: Geneva, Arial, Helvetica, sans-serif;
    }
</style>
