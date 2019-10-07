<template>
<div id="app">
    <Header></Header>
    <AppBody></AppBody>
    <Sidebar v-show="$route.path === '/Dashboard' || $route.path === '/Subjects'|| $route.path === '/EditProfile' ||  $route.path === '/PersonalInfo'? true: false "> -->
    </Sidebar>
</div>
</template>

<script>
import Sidebar from 'components/frame/Sidebar.vue'
import Header from 'components/frame/Header.vue';
import AppBody from 'components/frame/Body.vue'
export default {
    name: 'app',
    components: {
        Header,
        AppBody,
         Sidebar
    }
}
</script>
