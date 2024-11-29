<template>
    <div class="container bg-danger-subtle p-5 rounded-5">
        <h1 class="text-center">Calculadora
            <hr> 👩‍💻
        </h1>
        <InputField v-model="primeiro" />
        <SelectOperation v-model="operacao" />
        <InputField v-model="segundo" />
        <h2 class="rounded-pill text-center bg-success p-2">= {{ resultado }}</h2>
    </div>
</template>

<script>
import InputField from './InputField.vue';
import SelectOperation from './SelectOperation.vue';

export default {
    components: {
        InputField,
        SelectOperation
    },
    data() {
        return {
            primeiro: 0,
            segundo: 0,
            operacao: 'mais'
        };
    },
    computed: {
        resultado() {
            const num1 = parseFloat(this.primeiro);
            const num2 = parseFloat(this.segundo);
            console.log(`Primeiro: ${num1}, Segundo: ${num2}, Operação: ${this.operacao}`);
            switch (this.operacao) {
                case 'menos':
                    return num1 - num2;
                case 'mais':
                    return num1 + num2;
                case 'vezes':
                    return num1 * num2;
                case 'dividir':
                    return num2 !== 0 ? num1 / num2 : 'Erro: Divisão por zero';
            }
        }
    },
    watch: {
        primeiro(newVal) {
            console.log('primeiro foi alterado:', newVal);
        },
        segundo(newVal) {
            console.log('segundo foi alterado:', newVal);
        },
        operacao(newVal) {
            console.log('operacao foi alterado:', newVal);
        }
    }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Protest+Revolution&display=swap');

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
    font-family: "Protest Revolution", sans-serif;
    font-weight: 400;
}

input,
select {
    margin: 10px;
}

h2 {
    margin-top: 20px;
}
</style>