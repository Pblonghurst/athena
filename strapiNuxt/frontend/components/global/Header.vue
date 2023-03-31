<template>
    <div class="header">
        <div class="container">
            <nuxt-link class="header__item" to="/missions">Mission Cards</nuxt-link>
            <nuxt-link class="header__item" to="/events">Random Events</nuxt-link>
            <!-- <nuxt-link class="header__item" to="/heros">Heros</nuxt-link> -->
        </div>
    </div>
</template>

<style scoped lang="scss">
@import '../../assets/styles/global/header.scss';
</style>

<script>
export default {
    name: "Header"
}
</script>


