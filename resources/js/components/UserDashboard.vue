<template>
    <div class="user-dashboard">
        <div class="list-user-comp">
            <ListUser @userSelected="childrenSelectUser('text', ...arguments)"></ListUser>
        </div>
        <div class="user-detail-comp">
            <UserDetail :text="text" :userDetailInfo="userSelectedFromChild" :number="number" :string="string"></UserDetail>
        </div>
    </div>
</template>

<script>
import ListUser from './ListUser.vue';
import UserDetail from './UserDetail.vue';
export default {
    components: {
        ListUser,
        UserDetail
    },
    data() {
        return {
            text: '',
            userSelectedFromChild: {},
            number: 0,
            string: ''
        };
    },
    methods: {
        childrenSelectUser(text, user, number, string) {
            this.text = text;
            this.userSelectedFromChild = user;
            this.number = number;
            this.string = string;
        }
    }
}
</script>

<style scoped>

</style>

