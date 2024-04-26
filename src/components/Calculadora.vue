<script setup>
    const props = defineProps(['getNumero1', 'getNumero2', 'trocar-operacao', 'calcula-operacoes'])
</script>

<template>
    <div class="row justify-content-center">
        <div class="col-md-5">
            <h1 class="mt-5 mb-4">Calculadora Aritmética</h1>
        </div>
    </div>
    <div class="row justify-content-center">
        <div class="col-md-5 mb-3">
            <input class="form-control" type="number" placeholder="Digite o primeiro número" @input="props.getNumero1">
        </div>
    </div>
    <div class="row justify-content-center">
        <div class="col-md-5 mb-3">
            <input class="form-control" type="number" placeholder="Digite o segundo número" @input="props.getNumero2">
        </div>
    </div>
    <div class="row justify-content-center">
        <div class="col-md-5 mb-3">
            <select class="form-control" @change="props.trocarOperacao">
                <option value="adicao">Adição</option>
                <option value="subtracao">Subtração</option>
                <option value="multiplicacao">Multiplicação</option>
                <option value="divisao">Divisão</option>
            </select>
        </div>
    </div>
    <div class="row justify-content-center">
        <div class="col-md-5">
            <span class="h5">
                Resultado: {{ props.calculaOperacoes }}
            </span>
        </div>
    </div>
</template>