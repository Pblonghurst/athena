<template>
    <div class="cards-missions">
        <div class="container">
            <h1>Missions</h1>
        </div>
        <div class="container j-sb"> 
            <Card v-for="(item, index) in this.missions.data"
                :key="index"
                :keyIndex="index + 11"
                :title="item.attributes.title"
                :desc="item.attributes.description"
                :img="item.attributes.image.data.attributes.url"
                :imgSmall="item.attributes.imgSmall"
                :info="item.attributes.text"
            />
        </div>
    </div>
  </template>

<style lang="scss" scoped>
@import '../../assets/styles/cards/cards-missions.scss';
</style>
  
<script>
export default {
name: 'CardsMissions',
data(){
    return {
      missions: Object,
    }
  },
  methods: {
    async asyncData() {
        const missionsData = await fetch(
            this.$store.state.apiroute.url + '/api/missions'+ "?populate=deep,3"
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
  