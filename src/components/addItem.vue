<template>
    <form>
        <input type="text" placeholder="Введите название пункта">
        <button type="submit">Добавить</button>
    </form>
</template>

<style lang="scss" scoped>
    form {
        display: flex;
        align-items: stretch;
        margin: auto;
        width: 500px;
        margin-bottom: 20px;
    }
    input {
        flex: auto;
        margin-right: 5px;
        border: 1px solid #EAEAEA;
        padding: 10px 15px;
        border-radius: 5px 0 0 5px;
        &:focus {
            outline: dashed 2px grey;
        }
    }
    button {
        background: rgb(30, 189, 78);
        border-radius: 0 5px 5px 0;
        border: 1px solid #EAEAEA;
        color: white;
        outline: none;
        cursor: pointer;
    }
</style>