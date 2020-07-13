<template>
    <div>
        <ul>
            <todoItem
                v-for="key of todos"
                :todoIt = "key"
                @removeItem="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
import todoItem from '@/components/todoItem.vue';

export default {
  props: [
    'todos',
  ],
  components: {
    todoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-item', id)
    }
  }
};
</script>

<style scoped>
  ul {
    list-style: none;
    margin: auto;
    padding: 0;
    max-width: 500px;
  }
</style>