<script>
export default {
    name: "home",
    data() {
        return {
            posts: [],
        };
    },
    mounted() {
        fetch("https://jsonplaceholder.typicode.com/posts")
            .then((response) => response.json())
            .then((json) => (this.posts = json));
    },
};
</script>

<template>
    <div class="home container mx-auto">
        <h1 class="mb-2 text-center text-2xl font-bold text-green-500">
            Posts from APIs
        </h1>

        <div class="mb-5 grid grid-cols-1 gap-3 px-3 md:grid-cols-3">
            <div
                class="break-words rounded border border-gray-200 bg-gray-200 p-4"
                v-for="post in posts"
                :key="post.id">
                <h2
                    class="text-xl font-bold text-red-500 first-letter:capitalize">
                    {{ post.title }}
                </h2>
                <p class="first-letter:capitalize">{{ post.body }}</p>
            </div>
        </div>
    </div>
</template>
