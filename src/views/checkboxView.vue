<script>
import TodoItem from "@/components/TodoItem.vue";
export default {
  components: {
    TodoItem,
  },
  data() {
    return {
      groceryList: [
        { id: 0, text: "中文", selected: true },
        { id: 1, text: "英文", selected: false },
        { id: 2, text: "日文", selected: false },
      ],
    };
  },
};
</script>

<template>
  <ol>
    <!--
      We are providing each todo-item with the todo object
      it's representing, so that its content can be dynamic.
      We also need to provide each component with a "key",
      which is explained in the guide section on v-for.
    -->
    <TodoItem
      v-for="item in groceryList"
      :todo="item"
      :key="item.id"
    ></TodoItem>
  </ol>
</template>
