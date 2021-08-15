<template>
        <h2>Estado de Cuenta</h2>
        <p>Estado: <strong>{{status ? 'Activa' : 'Desactivada'}}</strong></p>
        <div v-if="status">
            <h3>Saldo: {{balance}}</h3>
            <ul>
                <li class="list-item" v-for="(item, index) in services" :key="index">{{index+1}} - {{item}}</li>
            </ul>
            <div class="mg-top">
                <ActionsForBalance textButton="Abonar Saldo" @modifyBalance="increaseBalance" />
                <ActionsForBalance textButton="Descontar Saldo" @modifyBalance="decreaseBalance" />
            </div>
        </div>
        
        
        
</template>

<script>
import ActionsForBalance from './ActionsForBalance.vue'

export default {
    components: {
        ActionsForBalance
    },
    data() {
        return {
            status: true,
            type: 'Visa',
            balance: 1200,
            base: 50,
            services: ['giro', 'abono', 'transferencia']
        }
    },
    methods: {
        increaseBalance () {
            this.balance += this.base;
        },
        decreaseBalance () {
            this.balance -= this.base;
        }
    }
}
</script>

<style>
    ul {
        padding-left: 0;
        width: 30%;
        margin: auto;
    }
    .list-item {
        list-style: none;
        text-align: left;
    }
    .mg-top {
        margin-top: 20px;
    }
</style>