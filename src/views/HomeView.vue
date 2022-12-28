<script>
export default {
    name: "home",
    data() {
        return {
            universities: [],
        };
    },
    mounted() {
        fetch("http://universities.hipolabs.com/search?country=Bangladesh")
            .then((response) => response.json())
            .then((json) => (this.universities = json));
    },
};
</script>

<template>
    <div class="home container mx-auto">
        <h1 class="mb-2 text-center text-2xl font-bold text-green-500">
            Universities list of Bangladesh
        </h1>

        <div class="mb-5 grid grid-cols-1 gap-3 px-3 md:grid-cols-3">
            <div
                class="break-words rounded border border-gray-200 bg-gray-200 p-4"
                v-for="university in universities"
                :key="university.id">
                <h2 class="text-xl font-bold text-red-500">
                    {{ university.name }}
                </h2>
                <p>Country: {{ university.country }}</p>
                <p>
                    Website:
                    <a :href="university.web_pages[0]" target="_blank">
                        {{ university.web_pages[0] }}</a
                    >
                </p>
            </div>
        </div>
    </div>
</template>
