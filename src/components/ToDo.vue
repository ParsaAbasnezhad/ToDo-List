<template>
    <div class="todo-list" aria-label="لیست کارها">
        <ul v-if="todosFilter && todosFilter.length > 0" id="todo-list">
            <li v-for="todoapp in todosFilter" :key="todoapp.id" :todo="todoapp" class="todo-item">
                <label class="myCheck">
                    <input type="checkbox" @click="changeStatus(todoapp.id, todoapp.isCompleted)"
                        :checked="todoapp.isCompleted" class="todo-item-checkbox" />
                    <span class="box"></span>
                    <span v-if="todoapp.isCompleted == true" class="todo-completed">{{ todoapp.title }}</span>
                    <span v-else v-text="todoapp.title" class="todo-item-text"></span>
                </label>

                <div class="btn-cheng-delet">
                    <button type="button" class="todo-item-delete">
                        <img src="style/svgs/Frame 6.svg" alt="" />
                    </button>
                    <button type="button" @click="deletToDO(todoapp.id)" class="todo-item-cheng">
                        <img src="style/svgs/trash-svgrepo-com 1.svg" alt="" />
                    </button>
                </div>
            </li>
        </ul>
        <div v-else>
            <img src="style/svgs/Detective-check-footprint 1.svg" alt="هیچ کاری وجود ندارد">
        </div>

    </div>
</template>

<script>
export default {
    props: {
        todos: {
            type: Array,
            required: true
        },
        todosFilter: {
            type: Array,
            required: true
        }
    },
    data() {
        return {

        }
    }, methods: {
        deletToDO(id) {
            if (confirm('آیا از حذف اطمینان دارید؟')) {
                this.$emit('DeletToDo', id)
            }
        },
        changeStatus(id, currentStatus) {
            this.$emit('chengStatus', id, !currentStatus);
        }
    },
}
</script>


<style scoped>
.todo-list {
    width: 720px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin: 0 auto;
}

#todo-list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    list-style: none;
    padding: 0;
    margin: 0;
    width: 650px;
}

.todo-item {
    width: 720px;
    display: flex;
    justify-content: space-between;
    gap: 450px;
    height: 50px;
    align-items: center;
    margin-top: 14px;
}


.myCheck {
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
}

.myCheck input[type="checkbox"] {
    appearance: none;
    width: 30px;
    height: 30px;
    margin: 0;
    cursor: pointer;
    border: 2px solid #aaa;
    border-radius: 4px;
    transition: border-color 0.3s ease;
}

.myCheck .box {
    position: absolute;
    width: 31px;
    height: 31px;
    pointer-events: none;
    border-radius: 4px;
    background: var(--color--bg);
    border: 2px solid var(--color--gray);
    transform: scale(1);
    transition: all 0.3s ease;
}

.myCheck input[type="checkbox"]:checked+.box {
    background: var(--color--gray);
    border-color: var(--color--gray);
    transform: scale(1.1);
}

.myCheck input[type="checkbox"]:hover+.box {
    border-color: var(--color--gray);
}

.todo-item-text {
    font-weight: 700;
    font-size: 20px;
    color: var(--color--black);
    cursor: pointer;
    margin-left: 1rem;
    width: auto;
}

.todo-completed {
    color: #9ca3af;
    text-decoration: line-through;
    text-decoration-thickness: 2px;
    text-decoration-color: #6b7280;
    transition: 0.2s ease;
}


.todo-item-id {
    font-weight: 700;
    font-size: 20px;
    color: var(--color--black);
    cursor: pointer;
}

.btn-cheng-delet {
    display: flex;
    align-items: center;
    gap: 10px;
}

.todo-item-delete,
.todo-item-cheng {
    border: none;
    background-color: transparent;
    width: 16px;
    height: 16px;
    cursor: pointer;
    margin-right: 10px;
    transition: all 0.3s ease;
    color: #f0f5ff;
}

/* .todo-item-delete.active {
  color: red;
}

.todo-item-cheng.active {
  color: #00d1b2;
} */

.todo-item-delete:hover,
.todo-item-cheng:hover {
    color: var(--color--gray);
}
</style>