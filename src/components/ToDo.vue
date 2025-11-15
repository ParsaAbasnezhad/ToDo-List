<template>
    <div class="todo-list" aria-label="لیست کارها">
        <ul id="todo-list">
            <li class="todo-item">
                <label class="myCheck">
                    <input type="checkbox" class="todo-item-checkbox" />
                    <span class="box"></span>
                    <span class="todo-item-text">Buy milk</span>
                    <span class="todo-item-id">#1</span>
                </label>
                <div class="btn-cheng-delet">
                    <button type="button" class="todo-item-delete">
                        <img src="style/svgs/Frame 6.svg" alt="" />
                    </button>
                    <button type="button" class="todo-item-cheng">
                        <img src="style/svgs/trash-svgrepo-com 1.svg" alt="" />
                    </button>
                </div>
            </li>
            <hr>
            <li class="todo-item">
                <label class="myCheck">
                    <input type="checkbox" class="todo-item-checkbox" />
                    <span class="box"></span>
                    <span class="todo-item-text">Buy milk</span>
                    <span class="todo-item-id">#1</span>
                </label>
                <div class="btn-cheng-delet">
                    <button type="button" class="todo-item-delete">
                        <img src="style/svgs/Frame 6.svg" alt="" />
                    </button>
                    <button type="button" class="todo-item-cheng">
                        <img src="style/svgs/trash-svgrepo-com 1.svg" alt="" />
                    </button>
                </div>
            </li>
            <hr>
        </ul>
    </div>
</template>

<script>
export default {

}
</script>
