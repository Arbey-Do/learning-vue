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
                <ActionsForBalance textButton="Descontar Saldo" @modifyBalance="decreaseBalance" :disabled="disabled"/>
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
            balance: 1000,
            base: 50,
            services: ['giro', 'abono', 'transferencia'],
            disabled: false
        }
    },
    methods: {
        increaseBalance () {
            if(this.disabled === true) { this.disabled = false }
            this.balance += this.base;
        },
        decreaseBalance () {
            if(this.balance >= this.base) {
                this.balance -= this.base
                if(this.balance === 0) {
                    this.disabled = true
                }
            }
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