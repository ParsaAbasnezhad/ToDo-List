<template>
  <div class="footer">
    <footer>
      <div class="icon-plus">
        <img src="style/svgs/plus.svg" alt="" />
      </div>
    </footer>
  </div>

</template>

<script>
export default {}
</script>

<style scoped>
.icon-plus {
  width: 50px;
  height: 50px;
  cursor: pointer;
  background-color: #6c63ff;
  border-radius: 50%;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  margin-left: 48rem;
}



.footer {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 10px;
}

.icon-plus img {
  margin-top: 15px;
  margin-left: 15px;
}
</style>