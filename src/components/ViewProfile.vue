<template>
    <div>
        <h1>Profile for {{ userId }}</h1>
    </div>
</template>

<script>
export default {
    name: 'ViewProfile',
    data() {
        return {
            userId: this.$route.params.user_id
        }
    },
    methods: {
        updateUserId() {
            this.userId = this.$route.params.user_id
        }
    },
    watch: {
        $route: 'updateUserId',
    }
}
</script>