<template>
    <div class="admin-post-page">
        <section class="new-post-form">
            <AdminPostForm @submit="onSubmitted"/>
        </section>
    </div>
</template>
<script>
    import axios from 'axios'
    import AdminPostForm from "@/components/Admin/AdminPostForm";

    export default {
        components: {
            AdminPostForm
        },
        methods: {
            onSubmitted(postData) {
                axios.post('https://nuxt-blog-67fb3.firebaseio.com/posts.json', {
                    ...postData,
                    updatedDate: new Date()
                })
                    .then(result => console.log(result))
                    .catch(e => console.log(e));
            }
        }
    }
</script>

<style scoped>
    .new-post-form {
        width: 90%;
        margin: 20px auto;
    }

    @media (min-width: 768px) {
        .new-post-form {
            width: 500px;
        }
    }

</style>
