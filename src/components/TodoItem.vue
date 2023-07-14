<script lang="ts">
import { defineComponent } from "@vue/runtime-dom";

declare interface todo {
  id: string;
  text: string;
  selected: boolean;
}

export default defineComponent({
  props: {
    todo: {
      type: Object as () => todo,
      required: true,
    },
  },
  data() {
    return {
      localSelected: this.todo.selected,
      localText: this.todo.text,
      localId: this.todo.id,
    };
  },
});
</script>

<template>
  <li>{{ todo.id }}</li>
  <input
    type="checkbox"
    :id="'test' + localId"
    :value="'test' + localId"
    v-model="localSelected"
  />
  <label :for="'test' + localId">{{ localText }}</label>
  <br />
  <table>
    <thead>
      <tr>
        <td>語言</td>
        <td>標題</td>
        <td>內文</td>
      </tr>
    </thead>
    <tbody>
      <td>{{ localText }}</td>
      <td>
        <input v-show="localSelected" v-model="localText" />
      </td>
      <td>
        <input v-show="localSelected" v-model="localText" />
      </td>
    </tbody>
  </table>
</template>
