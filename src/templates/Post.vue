<template>
    <Layout>
<div class="markdown-body">
     <h1>{{ $page.post.title }}</h1>
      <img :src="$page.post.featuredImage" alt="blog">
      <div v-html="$page.post.content" />
</div>
    </Layout>
</template>
<page-query>
query Post($path:String!){
  post:post(path:$path){
    title
    featuredImage
    content
  }
}
</page-query>
<script>
    export default {
        metaInfo(){
            return{
                title:this.$page.post.title
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>