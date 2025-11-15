<template>
    <div class="todo">
        <div class="controls" role="region" aria-label="کنترل‌ها">
            <label class="search" for="searchInput">
                <input id="searchInput" type="search" placeholder="Search note..." aria-label="جستجو" />
                <img class="search-icon" src="style/svgs/todo-app.svg" alt="" />
            </label>

            <select id="filterSelect" class="filter" aria-label="فیلتر">
                <option value="all">ALL</option>
                <option value="active">Active</option>
                <option value="done">Completed</option>
            </select>

            <button id="themeToggle" class="theme-toggle" type="button" aria-label="تغییر تم">
                <img src="style/svgs/Vector.svg" alt="" />
            </button>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style></style>