<template>
  <div>
    <input
      type="text"
      v-model="newTodoItem"
      placeholder="Add whatever you want"
      v-on:keyup.enter="addItem"
    />
    <button v-on:click="addItem">Add</button>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      newTodoItem: ""
    };
  },
  methods: {
    addItem: function() {
      // 로컬 저장소에 입력받은 데이터 추가
      // 키 / 값 형태
      if (this.newTodoItem === "") alert("No text input");
      else {
        localStorage.setItem(this.newTodoItem, this.newTodoItem);
        this.clearInput();
      }
    },
    clearInput: function() {
      this.newTodoItem = "";
    }
  }
};
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478fb, #8763fb);
  display: inline-block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
