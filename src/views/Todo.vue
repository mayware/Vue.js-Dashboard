<template>
    <div class="content">
        <div class="todo-block">
            <div class="todo-title">Todo list app</div>
            <div class="form-box">
                <div class="control-panel">
                    <div class="task-number">Task(s) {{ tasks }}:</div>
                </div>
                <div class="control-panel">
                    <div class="task-number">Completed:</div>
                </div>
                <div class="input-btn">
                    <input type="text" name="inputField" class="todo-input" placeholder="Type something..."
                        v-model="newTodo" @keyup.enter="addTodo">
                    <button type="submit" class="add-todo-btn" @click="addTodo">Add</button>
                </div>
            </div>
            <div class="todos">
                <div class="list-box" v-for="todo, index in todos" :key="todoId">
                    <div class="todo-text-check">
                        <input type="checkbox" class="check-box">{{ todo.body }}
                    </div>
                    <div class="edit-rem-btn">
                        <button class="edit-btn"><span class="material-symbols-outlined">edit</span></button>
                        <button class="remove-btn" @click="removeTodo(index)"><span
                                class="material-symbols-outlined">close</span></button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    data() {
        return {
            newTodo: '',
            todoId: 1,
            tasks: 0,
            completed: 0,
            todos: []
        }
    },
    methods: {
        addTodo() {
            if (this.newTodo !== '')
                this.todos.push({
                    id: this.todoId,
                    body: this.newTodo
                })
            this.newTodo = ''
            this.todoId++
            this.tasks++
        },
        removeTodo(index) {
            this.todos.splice(index, 1)
            this.tasks--
        }
    }
}
</script>
<style scoped>
.todo-block {
    display: grid;
    grid-template-columns: 1fr;
    gap: 10px;
    padding: 1.5rem;
    border-radius: 5px;
}

.todo-title {
    font-size: 24px;
    font-weight: 700;
    color: #adb5bd;
    margin-bottom: 1rem;
    text-align: center;
}

.form-box {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    justify-items: center;
    padding: 1rem;
    border-radius: 5px;
    background: #191919;
    box-shadow: 0px 0px 15px #000;
}

.control-panel {
    display: flex;
    align-items: center;
    padding: .5rem;
    border-radius: 5px;
    width: 100%;
}

.task-number {
    display: flex;
    align-items: center;
    margin-right: 1rem;

}

.input-btn {
    display: flex;
    align-items: center;
}

.todo-input {
    height: 35px;
    width: 450px;
    border: 2px solid transparent;
    background: #adb5bd;
    border-radius: 5px;
    padding: 0 .5rem 0 .5rem;
    margin-right: .5rem;
    transition: 200ms ease-in-out;
}

.todo-input:focus {
    outline: none;
    border: 2px solid #e63946;
    transition: 200ms ease-in-out;
}

.add-todo-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 35px;
    width: 75px;
    border: 1px solid transparent;
    border-radius: 5px;
    background: #003f88;
    font-size: 14px;
    font-weight: 500;
    color: #dee2e6;
    padding: .5rem;
    cursor: pointer;
    transition: 200ms ease-in-out;
}

.add-todo-btn:hover {
    border: 1px solid #adb5bd;
    background: #003566;
    transition: 200ms ease-in-out;
}

.todos {
    display: grid;
    grid-template-columns: 1fr;
    gap: 5px;
    padding: .5rem;
    background: #191919;
    box-shadow: 0px 0px 10px #000;
}

.list-box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem;
    border: 1px solid #343434;
    background: #212529;
    border-radius: 5px;
}

.todo-text-check {
    display: flex;
    align-items: center;
}

.check-box {
    margin-right: .5rem;
    background: #dee2e6;
    height: 20px;
    width: 20px;
}

.edit-rem-btn {
    display: flex;
    align-items: center;
}

.edit-btn {
    display: flex;
    align-items: center;
    border: 2px solid transparent;
    border-radius: 5px;
    margin-right: .5rem;
    background: #495057;
    color: #adb5bd;
    cursor: pointer;
    transition: 200ms ease-in-out;
}

.edit-btn:hover {
    background: #343a40;
    transition: 200ms ease-in-out;
}

.remove-btn {
    display: flex;
    align-items: center;
    border: 2px solid transparent;
    border-radius: 5px;
    background: #e63946;
    color: #adb5bd;
    cursor: pointer;
    transition: 200ms ease-in-out;
}

.remove-btn:hover {
    background: #d62828;
    transition: 200ms ease-in-out;
}
</style>