<template>
    <div class="lista-divisas">
        <h1>{{titulo}}</h1>
        <h2>{{convertirFecha}}</h2>
        <h1>{{divisaSeleccionada}}</h1>
        <ul>
            <Item
                    v-for="(value, key, index) of divisas"
                    v-bind:nombre="key"
                    v-bind:valor="value"
                    v-bind:key="index"
                    v-bind:handle-click="recibeDivisa"
            >
            </Item>
        </ul>
    </div>
</template>

<script>
    import Item from "./Item";
    export default {
        name: 'ListaDivisas',
        components: {
            Item
        },
        props: {
            titulo: String
        },
        data: function() {
            return {
                divisas: [],
                fecha: '',
                divisaSeleccionada: ''
            }
        },
        created: function() {
            const url = "https://api.frankfurter.app/latest";
            fetch(url)
            .then((response) => response.json())
            .then((data) => {
                console.log(data);
                this.divisas = data.rates;
                this.fecha = data.date;
            })
        },
        computed: {
            convertirFecha: function() {
                const fechaNumber = Date.parse(this.fecha);
                const fecha = new Date(fechaNumber);
                return `${fecha.getDate()}/${fecha.getMonth() + 1}/${fecha.getFullYear()}`;
            }
        },
        methods: {
            recibeDivisa: function(nombre, valor) {
                this.divisaSeleccionada = nombre + ': ' + valor;
            }
        }
    }
</script>

<style>
    .lista-divisas ul {
        margin: 0;
        padding: 0;
    }
</style>
