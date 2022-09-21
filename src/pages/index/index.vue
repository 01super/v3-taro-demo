<template>
  <view class="index">
    <Counter />
    <div>{{ count }}</div>
    <div>ojbk.age{{ ojbk.age }}</div>
    <button @click="add">add</button>
  </view>
</template>

<script setup>
import { ref, reactive, effect } from "vue";
import "./index.less";
import Counter from "../../components/Counter.vue";

const ojbk = reactive({
  age: 10
});

const count = ref(1);

effect(() => {
  ojbk.age = ojbk.age + count.value;
  console.log(ojbk.age, "init");
});

const add = () => {
  count.value++;
};
</script>
