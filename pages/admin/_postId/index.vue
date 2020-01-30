<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" />
    </section>
  </div>
</template>

<script>
  import AdminPostForm from "@/components/Admin/AdminPostForm";

  export default {
    layout: 'admin',
    components: {
      AdminPostForm
    },
    data () {
      return {
        loadedPost: {
          author: 'Vitali',
          title: 'My awesome Post',
          content: 'Super amazing',
          thumbnailLink: 'https://image.shutterstock.com/image-photo/mountains-during-sunset-beautiful-natural-260nw-407021107.jpg'
        }
      }
    }
  }
</script>
