<script>
export default {
    name: "App",
    data() {
        return {
            msg: "Welcome to your VueJS App!",
            courses: [
                {
                    id: 1,
                    name: "VueJS",
                    description:
                        "VueJS is a progressive framework for building user interfaces.",
                    price: 100,
                },
                {
                    id: 2,
                    name: "ReactJS",
                    description:
                        "ReactJS is a progressive framework for building user interfaces.",
                    price: 200,
                },
                {
                    id: 3,
                    name: "Laravel",
                    description:
                        "ReactJS is a progressive framework for building user interfaces.",
                    price: 300,
                },
            ],
        };
    },
    mounted() {
        this.test();
    },
    methods: {
        test() {
            this.msg = "Data changed!";
        },
    },
};
</script>

<template>
    <div class="container mx-auto">
        <h2 class="mb-3 text-3xl font-bold text-red-500">
            {{ msg }}
        </h2>

        <div
            v-for="course in courses"
            class="mb-4 rounded border border-gray-200 p-4 shadow">
            <h3 class="course-name text-2xl font-semibold text-green-400">
                {{ course.name }}
            </h3>
            <p class="py-2">{{ course.description }}</p>
            <p class="flex gap-1">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="h-6 w-6">
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M12 6v12m-3-2.818l.879.659c1.171.879 3.07.879 4.242 0 1.172-.879 1.172-2.303 0-3.182C13.536 12.219 12.768 12 12 12c-.725 0-1.45-.22-2.003-.659-1.106-.879-1.106-2.303 0-3.182s2.9-.879 4.006 0l.415.33M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
                {{ course.price }}
            </p>
        </div>

        <button
            class="rounded bg-black px-3 py-2 text-white"
            type="button"
            @click="test">
            Test
        </button>
    </div>
</template>

<style scoped>
h3.course-name {
    color: turquoise;
}
</style>
