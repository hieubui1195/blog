<template>
    <div class="my-component">
        <div>{{ reverseMessage }}</div>
        <div>
            <button @click="changeMessage">Click me</button>
        </div>

        <div>Message type: {{ objectMessage.type }}</div>
        <div>Message text: {{ objectMessage.text }}</div>
        <div>
            <button @click="changeObjectMessageType">Click change object message type</button>
        </div>
        <div>
            <button @click="changeObjectMessageText">Click change object message text</button>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: 'this is text',
                objectMessage: {
                    type: 'success',
                    text: 'Have been successed'
                }
            }
        },
        methods: {
            sayHello(text) {
                return text.toUpperCase()
            },
            changeMessage() {
                return this.message = 'message has been changed'
            },
            changeObjectMessageType() {
                return this.objectMessage.type = 'type of object message has been changed'
            },
            changeObjectMessageText() {
                return this.objectMessage.text = 'text of object message has been changed'
            }
        },
        computed: {
            reverseMessage() {
                return this.message.split('').reverse().join('')
            },
            getType() {
                return this.objectMessage.type
            },
            getText() {
                return this.objectMessage.text
            }
        },
        watch: {
            reverseMessage() {
                console.log('computed changed')
            },
            objectMessage: {
                handler: function () {
                    console.log('somthing changed, watch objectMessage')
                },
                deep: true
            },
            getType() {
                console.log('type changed')
            },
            getText() {
                console.log('text changed')
            }
        }
    }
</script>

<style lang="scss" scoped>
    .my-component {
        color: red;
    }
</style>