<template>
    <view>
        <view class="input-container">
            <text-input class="input-container__input" v-model="newTask" />
            <touchable-opacity class="input-container__btn" :on-press="newTodo">
                <image :source="require('../assets/plus.png')" class="input-container__btn__img"></image>
            </touchable-opacity>
        </view>

        <view class="Todo__card" v-for="todo in todos" :key="todo.id">
            <text class="Todo__card__text">{{ todo.name }}</text>
            <touchable-opacity class="Todo__card__btn" :on-press="() => eraseTodo(todo.id)">
                <image :source="require('../assets/trash.png')" class="todo__card__btn__img"></image>
            </touchable-opacity>
        </view>
    </view>
</template>

<script>
export default {
    data() {
        return {
            newTask: '',
            todos: [
                {
                    id: 0,
                    name: 'Faire le ménage'
                },
                {
                    id: 1,
                    name: 'Faire les courses'
                }
            ]
        }
    },
    methods: {
        newTodo() {
            if (this.newTask != '') {
                this.todos.push({
                id: this.todos.length + 1,
                name: this.newTask,
            })
            }
            this.newTask = ''
        },
        eraseTodo(id) {
           this.todos =  this.todos.filter(todo => todo.id !== id)
        }
    }
}
</script>

<style scoped>
    .input-container {
        flex-direction: row;
        justify-content: center;
        align-items: stretch;
    }
    .input-container__input {
        flex: 1;
        height: 40px;
        background-color: rgb(120, 131, 131);
        color: #323333;
        padding-left: 10px;
    }
    .input-container__btn {
        width: 90px;
        height: 40px;
        background-color: #3EB3F6;
        justify-content: center;
        align-items: center;
    }
    .input-container__btn__img {
       width: 15px;
       height: 15px;
    }
    .Todo__card {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;

        padding: 15px;
        background-color: #E0EDF4;
        border-left-color: #3EB3F6;
        border-left-width: 4px;
    }
    .Todo__card__text {
        color: #3E5252;
        font-size: 16px;
        font-weight: 500;
        margin-left: 5px;
    }
    .Todo__card__btn {
        align-items: center;
        justify-content: center;

        width: 30px;
        height: 30px;
        border-radius: 50px;
        background-color: rgb(212, 231, 241);
        margin-right: 16px;
    }
    .todo__card__btn__img {
        width: 12px;
        height: 12px;
    }
</style>