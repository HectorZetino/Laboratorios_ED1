<template>
    <div class="home">
        <h1>{{ msg }}</h1>
        <p>Ingrese el primer valor:</p>
        <p><input v-model="x1" placeholder="Primer Valor" /></p>
        <br />
        <p>Ingrese el segundo valor:</p>
        <p><input v-model="x2" placeholder="Segundo Valor" /></p>
        <br />
        <hr color="red">
        <p><button class="button" @click="plusMethod">SUMA</button></p>
        <span> {{_plus}}</span>
        <hr color="red">
        <p><button class="button" @click="subMethod">RESTA</button></p>
        <span>{{_sub}}</span>
        <hr color="red">
        <p><button class="button" @click="multiMethod">MULTIPLICACION</button></p>
        <span>{{_multi}}</span>
        <hr color="red">
        <p><button class="button" @click="divMethod">DIVISION</button></p>
        <span>{{_div}}</span>


    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class Home extends Vue {
        @Prop() private msg!: string;

         x1: number = 0
         x2: number = 0
        _plus: number = 0
        _sub: number = 0
        _multi: number = 0
        _div: number = 0
        _sqRoot: number = 0

        plusMethod() {
            this._plus = this.x1 + this.x2;
        }
        subMethod() {
            this._sub = this.x1 - this.x2;
        }
        multiMethod() {
            this._multi = this.x1 * this.x2;
        }
        divMethod() {
           
            this._div = this.x1 / this.x2;
        }
       
       

    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .button {
        border: solid;
        border-radius: 5px;
        background-color: #45a20d;
        font-size: 15px;
    }
</style>
