<template>
    <div class="conditional-rendering">
        <div class="block-1" v-if="isActive == true">
            This is block 1
        </div>
        <div class="block-2" v-else>
            This is block 2
        </div>
        <div>
            <button @click="toggleActive">Toggle Active</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isActive: true
        }
    },
    methods: {
        toggleActive() {
            this.isActive = !this.isActive
        }
    }
}
</script>

<style scoped>

</style>

