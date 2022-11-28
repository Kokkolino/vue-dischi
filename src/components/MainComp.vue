<template>
    <div>
        <div>
            <select v-model="genreFilter">
                <option value="" >All</option>
                <option value="rock">Rock</option>
                <option value="pop">Pop</option>
                <option value="jazz">Jazz</option>
                <option value="metal">Metal</option>
            </select>
        </div>
        <div id="container" v-if="albumsArr.length > 9">
            <TrackComp
            v-show="element.genre.toLowerCase().includes(genreFilter.toLowerCase())"
            v-for="(element, index) in albumsArr"
            :key="index"
            :album="element"
            />
        </div>
    </div>

</template>

<script>
    import TrackComp from "./elements/TrackComp.vue"
    import axios from 'axios'

    export default {
        name: 'MainComp',
        components: {
            TrackComp
        },
        data(){
            return{
                albumsArr: [],
                genreFilter: ""
            }
        },
        mounted(){
            this.CompileAlbums();
        },
        methods: {
            CompileAlbums(){
                axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((response) => {
                    this.albumsArr = response.data.response;
                    console.log(this.albumsArr)
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    #container{
        width: 75%;
        height: calc( 100% - 90px );
        margin: auto;
        padding: 40px;
        display: flex;
        justify-content: space-evenly;
        align-content: center;
        flex-wrap: wrap;
    }

</style>