<template>
    <v-layout row wrap>
        <Stock v-for="stock in stocks" :key="stock.id" :stock='stock' />
    </v-layout>
</template>

<script>
import Stock from './Stock'

export default {
    components: {Stock},

    data() {
        return {
            stocks: [
                {id: 1, name: 'BMW', price: 100},
                {id: 2, name: 'BMW2', price: 102},
                {id: 3, name: 'BMW3', price: 103},
            ]
        }
    }

}
</script>

<style>

</style>
