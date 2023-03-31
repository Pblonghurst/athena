<template>
    <div class="cards-events">
        <div class="container">
            <h1>Events</h1>
        </div>
        <div class="container j-sb"> 
            <Card v-for="(item, index) in this.missions.data"
                :key="index"
                :keyIndex="index + 11"
                :title="item.attributes.title"
                :desc="item.attributes.description"
                :img="item.attributes.image.data.attributes.url"
                :imgSmall="item.attributes.imgSmall"
                :bgColor="item.attributes.type.data.attributes.color"
            />
        </div>
    </div>
  </template>

<style lang="scss" scoped>
@import '../../assets/styles/cards/cards-events.scss';
</style>
  
<script>
export default {
name: 'CardsEvents',
data(){
    return {
      missions: Object,
    }
  },
  methods: {
    async asyncData() {
        const missionsData = await fetch(
            this.$store.state.apiroute.url + '/api/events'+ "?populate=deep,3"
        ).then((res) => {
            // can set up 404 redirection here
            return res.json();
        });
        this.missions = missionsData
        console.log('missions', this.missions)
    }
  },
  mounted(){
    this.asyncData();
  }
}
</script>
  