<template>
    <div class="list-rendering">
        <div>List of Foods</div>
        <ul>
            <li v-for="(food, index) in foods" :key="index">
                {{ food.name }} - at index: {{ index }}
            </li>
        </ul>
        <div>My info</div>
        <ul>
            <li v-for="(value, key) in myInfo" :key="key">
                {{ key }} - {{ value }}
            </li>
        </ul>
        <div>List complete to do</div>
        <ul>
            <li v-for="(toDo, index) in listCompleteToDo" :key='index'>
                {{ toDo.name }} - {{ toDo.isComplete }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            foods: [
                {name: 'Hamburger'},
                {name: 'Sandwich'},
                {name: 'Chicken'}
            ],
            myInfo: {
                name: 'Bui Thi Hieu',
                age: 23,
                country: 'Viet Nam'
            },
            todos: [
                {
                    name: 'To do 1',
                    isComplete: true
                },
                {
                    name: 'To do 2',
                    isComplete: false
                },
                {
                    name: 'To do 3',
                    isComplete: true
                }
            ]
        }
    },
    computed: {
        listCompleteToDo() {
            return this.todos.filter(item => item.isComplete)
        }
    }
}
</script>

<style scoped>

</style>

