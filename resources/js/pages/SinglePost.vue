<template>
  <main class="container">
    <div class="row">
        <div class="col-12">
            <div class="d-flex flex-wrap justify-content-center">
                <PostCard :key="post.id" :post="post" />
            </div>
        </div>
    </div>
  </main>
</template>

<script>
    import PostCard from '../components/PostCard.vue';
    import axios from 'axios';

    export default {
        components: {
            PostCard,
        },

        data: function(){
            return{
                post: {},
                loading: false,
            }
        },

        methods: {

            getPost(){
                const id = this.$route.params.id;

                axios.get( `/api/posts/${id}`).then((response) => {
                    this.post = response.data.results.data;
                    this.loading = false;
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