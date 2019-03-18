<template>
  <div id="app">
    <TodoHeader> </TodoHeader> <TodoInput></TodoInput> <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
// 컴포넌트를 불러온다
// 앱 이름표시
import TodoHeader from "./components/TodoHeader.vue";
// 할일 모두삭제
import TodoFooter from "./components/TodoFooter.vue";
// 할일 입력 및 추가
import TodoInput from "./components/TodoInput.vue";
// 할일 목록 표시 / 특정 할일 삭제
import TodoList from "./components/TodoList.vue";

export default {
  // 생성한 4개의 컴포넌트를 등록한다
  components: {
    TodoHeader: TodoHeader,
    TodoList: TodoList,
    TodoInput: TodoInput,
    TodoFooter: TodoFooter
  }
};
</script>

<style>
body {
  text-align: center;
  background-color: #f6f6f8;
}
input {
  border-style: groove;
  width: 200px;
}
button {
  border-style: groove;
}
.shadow {
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
}
</style>
