<template>
     <!-- Propriedades do flex da pra fazer responsivo -->
    <v-flex class="pr-3 pb-3" xs12 md6 lg4>
        <v-card class="green darken-3 white--text">
            <v-card-title class="headline">
                <strong> {{ stock.name }} <small>(preço: {{ stock.price }})</small></strong>
            </v-card-title>
        </v-card>
        <v-card>
            <v-container fill-height>
                <v-text-field label="Quantidade" type="number" v-model.number="quantity"> </v-text-field>
                <v-btn 
                    :disabled="quantity <= 0 || !Number.isInteger(quantity)"
                    @click="stockBuy"
                    class="green darken-3 white--text"> Comprar</v-btn>
            </v-container>
        </v-card>
    </v-flex>
</template>

<script>

export default {
    props: ['stock'],
    data() {
        return {
            quantity: 0
        }
    },
    methods: {
        stockBuy() {
            const order = {
                stockId : this.stock.id,
                stockPrice : this.stock.price,
                quantity : this.quantity
            }
            this.quantity = 0
            console.log(order)
        }

    }
  

}
</script>

<style>

</style>
