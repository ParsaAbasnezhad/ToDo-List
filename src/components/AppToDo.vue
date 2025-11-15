<template>
    <div class="todo">
        <div class="controls" role="region" aria-label="کنترل‌ها">
            <label class="search" for="searchInput">
                <input class="" v-model="title" @keyup.enter="AddToDo" id="searchInput" type="text"
                    placeholder="Search note..." aria-label="جستجو" />
                <img class="search-icon" src="style/svgs/todo-app.svg" alt="" />
                <button @click="AddToDo" id="themeToggle" type="button" class="search-button">ADD</button>
            </label>

            <select id="filterSelect" class="filter" aria-label="فیلتر">
                <option value="all">ALL</option>
                <option value="active">SERCH</option>
            </select>

            <button id="themeToggle" class="theme-toggle" type="button" aria-label="تغییر تم">
                <img src="style/svgs/Vector.svg" alt="" />
            </button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: "",
        };
    },
    methods: {
        AddToDo() {
            this.$emit('AddNewToDo', this.title);
            this.title = "";
        }
    }
}
</script>

<style scoped>
.controls {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-top: 20px;
    margin-bottom: 20px;
}

#searchInput {
    width: 595px;
    height: 26px;
    border-radius: 8px;
    border: 3px solid #6c63ff;
    background-color: #f7f7f7;
    padding: 10px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    font-size: 16px;
    outline: none;
}

.search-icon {
    top: 15px;
    left: 15px;
    width: 30px;
    height: 30px;
    position: relative;
    left: -52px;
    margin-bottom: 5px;
}

#filterSelect {
    width: 140px;
    height: 49px;
    border-radius: 8px;
    color: #f7f7f7;
    border: none;
    background-color: #6c63ff;
    padding: 10px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    font-size: 22px;
}

#themeToggle {
    background-color: #6c63ff;
    width: 50px;
    height: 50px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    margin-left: 10px;
    margin-right: 9px;
    margin-top: 2px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    color: aliceblue;
    font-size: 21px;
    font-weight: 500;
}
</style>