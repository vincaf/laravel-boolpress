<template>
  <main class="container">
    <div class="row">
        <div class="col-12">
            <div v-if="isLoading" class="loader text-center p-5 m-5">
                <MainLoader />
            </div>
            <div v-else class="d-flex flex-wrap justify-content-center">
                <PostCard :key="post.id" :post="post" />
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
        name: 'SinglePost',
        components: {
            PostCard,
            MainLoader,
        },

        data: function(){
            return{
                post: {
                    user:''
                },
                isLoading: true,
            }
        },

        methods: {

            getPost(){
                const id = this.$route.params.id;

                axios.get( `/api/posts/${id}`).then((response) => {
                    this.post = response.data.results.data;
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
    .ms_current_page{
        padding: 2px 8px;
        border: 2px solid #74afe0;
    }
</style>