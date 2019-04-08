<template>
    <div id="app">
        <h1>SnipTag</h1>
        <div id="nav">
            <router-link to="/">Filter</router-link> |
            <router-link to="/add">Add rsrc</router-link> |
            <router-link to="/tags">Tags (edit/add/del)</router-link>
        </div>
        <transition name="fade">
            <router-view />
        </transition>
    </div>
</template>
<style lang="scss" scoped>
.fade-enter-active,
.fade-leave-active {
    transition: all 0.3s ease;
}

.fade-enter,
.fade-leave-to {
    position: absolute;
    opacity: 0;
    transform: translateX(100%);
}
</style>
