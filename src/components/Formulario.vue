<script setup>
const props = defineProps(['filtraQualOperacao', 'pegaNum1', 'pegaNum2', 'trocarOperacao'])
</script>


<template>
    <form>
        <div class="row mb-4">
            <div class="col-4">
                <input @change="props.pegaNum1" type="number" class="bg-light form-control text-center" required
                    placeholder="Digite um número">
            </div>
            <div class="col-1">
                <span class="form-control justify-content-center d-flex bg-light" v-if="props.filtraQualOperacao === 'adicao'">+</span>
                <span class="form-control justify-content-center d-flex bg-light" v-else-if="props.filtraQualOperacao === 'subtracao'">-</span>
                <span class="form-control justify-content-center d-flex bg-light" v-else-if="props.filtraQualOperacao === 'multiplicacao'">x</span>
                <span class="form-control justify-content-center d-flex bg-light" v-else="props.filtraQualOperacao === 'divisao'">/</span>
            </div>
            <div class="col-4">
                <input @keyup="props.pegaNum2" type="number" class="form-control text-center bg-light" required
                    placeholder="Digite um número">
            </div>
            <div class="col-3">
                <select @change="props.trocarOperacao" class="form-control text-center bg-light">
                    <option value="adicao">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>