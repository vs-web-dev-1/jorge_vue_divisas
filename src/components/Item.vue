<template>
    <li
            class="item"
            v-on:click="handleClick(nombre, valor)"
    >
        {{nombre}}: {{valor}}
    </li>
</template>

<script>
    export default {
        name: 'Item',
        props: {
            nombre: String,
            valor: Number,
            handleClick: Function
        },
    }
</script>

<style>
    .item {
        list-style: none;
        border: 1px solid #666;
        padding: 4px 10px;
        margin: 5px auto;
        display: block;
        width: 150px;
        cursor: pointer;
    }
</style>
