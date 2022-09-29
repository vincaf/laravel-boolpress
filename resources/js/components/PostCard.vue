<template>
  <div class="card text-center m-3" style="width: 20rem;">
    <div class="card-header"> {{ post.user.name }} </div>
    <div class="card-image p-2">
        <img :src="isValidURL(post.post_image) ? post.post_image : 'storage/' + post.post_image" class="image-card" :alt="post.title">
    </div>
    <div class="card-body">
      <h5 class="card-title"> {{ post.title }} </h5>
      <p class="card-text">
        {{ post.post_content.substring(0, 100) }}
      </p>
    </div>
    <div class="card-footer text-muted"> {{ post.post_date }} </div>
  </div>
</template>

<script>
export default {
  props: ["post"],
  methods:{
    isValidURL(string) {
      var regex = /(?:https?):\/\/(\w+:?\w*)?(\S+)(:\d+)?(\/|\/([\w#!:.?+=&%!\-\/]))?/;
      if(!regex .test(string)) {
        return false;
      } else {
        return true;
      }
    },
  }
};
</script>

<style lang="scss" scoped>
.image-card{
  width: 300px;
  height: 250px;
  object-fit: cover;
}
</style>