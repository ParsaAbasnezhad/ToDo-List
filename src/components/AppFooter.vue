<template>
  <div class="footer">
    <footer>
      <div @click="addNodeText" class="icon-plus">
        <img src="style/svgs/plus.svg" alt="" />
      </div>
    </footer>
  </div>
  <div>
    <div v-if="addNode" class="cardPlus">
      <div class="cardPlus-content">
        <h1 class="cardPlus-title">New Note</h1>
        <div class="form-add-note">
          <div class="cardPlus-input">
            <input type="text" placeholder="Input your note..." class="cardPlus-input-text">
          </div>
          <div class="cardPlus-button">
            <button class="cardPlus-button-add">APPLY</button>
            <button @click="addNode = false" class="cardPlus-button-cancel">CANCEL</button>
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
      addNode: false
    }
  },
  methods: {
    addNodeText() {
      this.addNode = true;
    }
  }
}
</script>

<style scoped>
.icon-plus {
  width: 50px;
  height: 50px;
  cursor: pointer;
  background-color: var(--color--gray);
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


.cardPlus {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.45);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
  backdrop-filter: blur(2px);
}


.cardPlus-content {
  background: var(--color--bg) !important;
  width: 500px;
  height: 300px;
  padding: 22px;
  border-radius: 15px;
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.35);
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}

.cardPlus-title {
  color: var(--color--black);
  box-shadow: 0px 1px 0px rgba(0, 0, 0, 0.25);
  margin-bottom: 86px;
}

.form-add-note {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 60px;

}

.cardPlus-input-text {
  width: 400px;
  height: 40px;
  border: 1px solid var(--color--gray);
  border-radius: 8px;
  outline: none;
  font-size: 20px;
  background-color: var(--color--bg);
  color: var(--color--black);
  cursor: pointer;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

.cardPlus-button {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 313px;

}

.cardPlus-button-add {
  width: 100px;
  height: 40px;
  border: none;
  border-radius: 8px;
  font-size: 20px;
  background-color: var(--color--gray);
  color: var(--color--bg);
  cursor: pointer;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

.cardPlus-button-cancel {
  width: 100px;
  height: 40px;
  border: 1px solid;
  border-radius: 8px;
  font-size: 20px;
  background-color: var(--color--bg);
  color: var(--color--gray);
  cursor: pointer;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
</style>