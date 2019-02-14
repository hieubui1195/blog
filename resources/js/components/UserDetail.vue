<template>
    <div class="user-detail">
        <h3>User detail</h3>
        <h4 v-if="text.length !== 0">{{ text }}</h4>
        <h4 v-if="number !== 0">{{ number }}</h4>
        <h4 v-if="string.length !== 0">{{ string }}</h4>
        <div v-if="Object.keys(userDetailInfo).length !== 0">
            <div>
                Name: {{ userDetailInfo.name.last }} {{ userDetailInfo.name.first }}
            </div>
            <div>
                Email: {{ userDetailInfo.email }}
            </div>
            <div>
                DOB: {{ userDetailInfo.dob }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        text: {
            type: String
        },
        userDetailInfo: {
            type: Object
        },
        number: {
            type: Number
        },
        string: {
            type: String
        }
    },
}
</script>

<style lang="scss" scoped>

</style>

