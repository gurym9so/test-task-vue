<template>
  <div v-if="isVisible">
    <div class="popup">
      <h2>Форма</h2>
      <div class="input-container">
        <input
          type="text"
          placeholder="Имя"
          v-model="inputValue.nameInput.value"
        />
        <input
          type="text"
          placeholder="Логин"
          v-model="inputValue.loginInput.value"
        />
        <input
          type="text"
          placeholder="Пароль"
          v-model="inputValue.passwordInput.value"
        />
        <input
          type="text"
          placeholder="Почта"
          v-model="inputValue.emailInput.value"
        />
        <input
          type="text"
          placeholder="Номер"
          v-model="inputValue.numberInput.value"
        />
      </div>
      <button class="submit-button" @click="submitData">Отправить</button>
    </div>
    <div class="overlay" @click="hidePopup"></div>
  </div>
  <div v-if="isVisibleList">
    <inputList :inputValue="inputValue" />
  </div>
</template>

<script>
import inputList from "@/components/UI/inputList.vue";
export default {
  components: { inputList },
  data() {
    return {
      isVisible: true,
      isVisibleList: false,
      inputValue: {
        nameInput: {
          name: "Имя",
          value: "",
        },
        loginInput: {
          name: "Логин",
          value: "",
        },
        passwordInput: {
          name: "Пароль",
          value: "",
        },
        emailInput: {
          name: "Электронная почта",
          value: "",
        },
        numberInput: {
          name: "Номер телефона",
          value: "",
        },
      },
    };
  },
  methods: {
    hidePopup() {
      this.isVisible = false;
    },
    submitData() {
      this.isVisible = false;
      this.isVisibleList = true;
    },
  },
};
</script>

<style>
.overlay {
  display: block;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 999;
}
.popup {
  display: block;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  padding: 20px;
  max-width: 500px;
  width: 100%;
  border-radius: 5px;
  z-index: 1000;
}
.input-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.input-container input {
  margin-bottom: 10px;
}

.submit-button {
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
</style>
