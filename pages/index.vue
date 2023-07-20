<template>
    <div>
        <NuxtLink to="/posts">go blog</NuxtLink>
        <div v-if="!loading && error">
            {{ error }}
        </div>
        <div>
            {{ posts }}
            <button @click="signIn(undefined, { callbackUrl: '/' })">
                sign in
            </button>
            <br>
            <button @click="signIn('github', { callbackUrl: '/' })">
                sign in (github)
            </button>
            <br>
            <button @click="signIn('credentials', { username: 'jsmith', password: 'hunter2' })">
                Username and Password
            </button>
            <br>
            <button @click="signOut">
                sign out
            </button>
        </div>
    </div>
</template>

<script setup>

const { data: posts, pending, error, refresh } = await useFetch('/api/posts',{
})

</script>
