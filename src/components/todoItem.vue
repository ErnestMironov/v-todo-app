<template>
    <li>
      <label v-bind:class="{done: todoIt.completed}">
        <input type="checkbox" v-on:change="todoIt.completed = !todoIt.completed">
        <strong class="numb">{{todoIt.id}}</strong>
        <span>
          {{ todoIt.title }}
        </span>
      </label>
      <button class="delete" @click="$emit('removeItem', todoIt.id)">&times;</button>
    </li>
</template>

<script>
export default {
  props: {
    todoIt: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
  li {
    border: 1px solid #EAEAEA;
    border-radius: 5px;
    padding: 8px 12px;
    margin-bottom: 5px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  label {
    display: flex;
    align-items: flex-end;
  }

  .delete {
    display: flex;
    justify-content: center;
    height: 18px;
    width: 18px;
    align-items: center;
    background: #df3737;
    color: #FFF;
    border-radius: 50%;
    border: 0;
    cursor: pointer;
    transition: all ease-out .2s;
    
    &:hover {
      background: #ac2b2b;
    }
    &:focus {
      outline: 0;
    }
  }

  .done {
    text-decoration: line-through;
  }

  .numb {
    margin-right: 5px;
  }

  input {
    margin-right: 15px;
  }
</style>