<template>
    <div class="tabs">

        <!-- tabs buttons -->
        <div class="tabs__buttons">
            <div class="container">
                <ButtonCustom v-for="(button, index) in buttons"
                    :key="index"
                    :index="index"
                    :class="{ 'active': isActive == index }" 
                    :text="button.label"
                    @button-click="onTabClick"
                />
            </div>
        </div>

        <!-- window -->
        <div class="window">
            <div class="container j-sb">
                <div 
                    class="window__item"
                    :index="1"
                    v-if="isActive == 0"
                >
                    <h1>test one</h1>
                </div>
                <div 
                    class="window__item"
                    :index="2"
                    v-if="isActive == 1"
                >
                    <h1>test two</h1>
                </div>
            </div>
        </div>

    </div>
</template>

<style lang="scss" scoped>
@import '../../assets/styles/tabs/tabs.scss';
@import '../../assets/styles/windows/window.scss';
</style>

<script>
export default {
    name: "Tabs",
    data() {
        return {
            isActive: false,
            buttons: [
                { label: 'Button 1' },
                { label: 'Button 2' },
            ],
        };
    },
    methods: {
        onTabClick(index) {
            this.isActive = index
            console.log(`Tab button clicked ${index}`);
        },
    },
}
</script>

