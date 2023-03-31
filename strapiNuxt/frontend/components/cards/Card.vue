<template>
    <div class="card">
        <div class="card__num">
            <h4>{{ this.keyIndex }}</h4>
        </div>
        <img v-if="img" :src="$store.state.apiroute.url + img"
        :class="{ 
            'small': imgSmall,}" 
        />
        <div class="card__info"> 
            <h2>{{ this.title }}</h2>

            <div v-if="this.desc"> 
                <div class="card__info__text"> 
                    <vue-markdown :source="this.desc" />
                </div>
            </div>
            
            <div v-if="this.info"> 
                <div v-for="(item, index) in this.info" 
                :key="index"
                class="card__info__text"> 
                    <vue-markdown class="markdown" :source="item.description" />
                    <div class="card__info__text__vp">
                        <h3>{{ item.vp }}vp</h3>
                    </div>
                </div>
            </div>
     
        </div>
        <div 
            class="card__type"
            :style="{ 
                borderBottom: 'solid' + ' 30px ' + bgColor,
                borderRight: 'solid' + ' 30px ' + bgColor,
            }"
        ></div>
    </div>
</template>

<style lang="scss">
@import '../../assets/styles/cards/card.scss';
</style>

<script>
import VueMarkdown from 'vue-markdown';
export default {
    name: "Card",
    components: {
        VueMarkdown
    },
    props: {
        title: String,
        info: Array,
        img: String,
        desc: String,
        keyIndex: Number,
        imgSmall: Boolean,
        bgColor: String,
    }
}
</script>


