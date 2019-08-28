<template>
    <div >

        <h1>{{ msg }}</h1>
        <hr style="height: 10px; background-color: black;" color="Black" />
        <p>Gracias por utilizar el programa</p>
        <p>Ingrese el primer valor:</p>
        <p><input v-model.number="numero1"/></p>
        <hr style="height: 5px; background-color: black;" color="Black" />
        <p>Ingrese el segundo valor:</p>
        <p><input v-model.number="numero2"  /></p>

        <hr style="height: 5px; background-color: darkblue;" color="Blue" />
        <p><button class="button" @click="plusMethod">SUMA</button></p>
        <span> el resultado es: {{_plus}}</span>
        <hr style="height: 5px; background-color: darkblue;" color="Blue" />
        <p><button class="button" @click="subMethod">RESTA</button></p>
        <span> el resultado es: {{_sub}}</span>
        <hr style="height: 5px; background-color: darkblue;" color="Blue" />
        <p><button class="button" @click="multiMethod">MULTIPLICACION</button></p>
        <span> el resultado es: {{_multi}}</span>
        <hr style="height: 5px; background-color: darkblue;" color="Blue" />
        <p><button class="button" @click="divMethod">DIVISION</button></p>
        <span> el resultado es: {{_div}}</span>
        <hr style="height: 5px; background-color: darkblue;" color="Blue" />

    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class Home extends Vue {
        @Prop() private msg!: string;

         
        _plus: number = 0
        _sub: number = 0
        _multi: number = 0
        _div: number = 0
        _sqRoot: number = 0
        numero1: number = 0
        numero2: number = 0 

        plusMethod() {
            this._plus = (this.numero1) + (this.numero2)
            
        }
        subMethod() {
            this._sub = (this.numero1) - (this.numero2)
        }
        multiMethod() {
            this._multi = (this.numero1) * (this.numero2)
        }
        divMethod() {
            this._div = (this.numero1) / (this.numero2)
        }
       
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .button {
        border: solid;
        border-radius: 5px;
        background-color: #f00;
        font-size: 15px;
    }
</style>
