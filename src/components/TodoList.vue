<template>
  <div>
    <ul>
      <li v-for="item in todoItems" v-bind:key="item">
        <i class="checkBtn">{{ item }}</i>
        <span class="removeBtn" type="button" @click="removeItems(item, idx);">
          <i></i>
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  // 이처럼 키:값 쌍을 반환하는 식으로 데이터 등록
  data: function() {
    return {
      todoItems: []
    };
  },
  created() {
    // 인스턴스 생성 후 화면 부착되기 전 단계
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.todoItems.push(localStorage.key(i));
      }
    }
  }
};
</script>

<style scoped>
ul {
  list-style-type: none;
  padding-left: 0px;
  margin-top: 0;
  text-align: left;
}
li {
  display: flex;
  min-height: 50px;
  height: 50px;
  line-height: 50px;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  background: white;
  border-radius: 5px;
}
.checkBtn {
  line-height: 45px;
  color: #62acde;
  margin-right: 5px;
}
.removeBtn {
  margin-left: auto;
  color: #de4343;
}
.list-enter-active,
.list-leave-active {
  transition: all 1s;
}
.list-enter,
.list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
</style>
