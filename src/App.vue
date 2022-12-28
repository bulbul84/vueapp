<template>
    <div class="container mx-auto">
        <nav class="flex gap-3">
            <RouterLink to="/">Home</RouterLink>
            <RouterLink to="/about">About</RouterLink>
            <RouterLink to="/testing">Testing</RouterLink>
        </nav>
    </div>

    <RouterView />
</template>
