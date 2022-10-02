<template>
    <main class="container">
    <div class="row">
        <div class="col-12">
            <div v-if="isLoading" class="loader text-center p-5 m-5">
                <MainLoader />
            </div>

            <div v-else class="tag-container">
              <h1 class="p-3 m-3">
                  Avaible tags:
              </h1>

              <div class="d-flex flex-wrap justify-content-between">
                  <GenericCard v-for="tag in tags" :key="tag.id" :cardElement="tag" />
              </div>
            </div>
        </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import GenericCard from '../components/GenericCard.vue';
import MainLoader from '../components/MainLoader.vue';

export default {
    components:{
        GenericCard,
        MainLoader,
    },
    name: 'TagsIndexPage',
    data: function(){
        return{
            tags: [],
            currentPage: 1,
            lastPage: null,
            isLoading: true,
        }
    },

    methods:{
        getTags(tagsPage = 1){
            axios.get('/api/tags' , {
                    params: {
                        page: tagsPage,
                    }
            }).then((response) => {
                // console.log(response.data.results);
                console.log(response.data.results.data);
                this.tags = response.data.results.data;
                this.currentPage = response.data.results.current_page;
                this.lastPage = response.data.results.last_page;
                this.isLoading = false;

            }).catch((error) => {
                console.error(error);
            })
        },
    },

    created(){
        this.getTags();
    }
}
</script>

<style>

</style>