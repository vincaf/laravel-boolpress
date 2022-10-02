<template>
  <main class="container">
    <div class="row">
        <div class="col-12">
            <div v-if="isLoading" class="loader text-center p-5 m-5">
                <MainLoader />
            </div>

            <div v-else class="post-container">
              <h1 class="p-3 m-3">
                  Tag: {{ tag.name }}
              </h1>

              <div class="d-flex flex-wrap justify-content-between">
                  <PostCard v-for="post in tag.posts" :key="post.id" :post="post" />
              </div> 
            </div>
        </div>
    </div>
  </main>
</template>

<script>
    import PostCard from '../components/PostCard.vue';
    import MainLoader from '../components/MainLoader.vue';
    import axios from 'axios';

    export default {
        name: 'TagPostsList',
        components: {
            PostCard,
            MainLoader,
        },

        data: function(){
            return{
                tag: {
                    post: ''
                },
                isLoading: false,
            }
        },

        methods: {

            getPost(){
                const id = this.$route.params.id;

                axios.get( `/api/tags/${id}`).then((response) => {
                    this.tag = response.data.results.data;
                    this.isLoading = false;
                }).catch((error) => {
                    console.error(error);
                })
            }
        },

        created(){
            this.getPost();
        }
    }
</script>

<style lang="scss" scoped>

</style>