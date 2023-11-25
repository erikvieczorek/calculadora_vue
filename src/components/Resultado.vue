<script setup>
const props = defineProps(['filtraOperacao'])
</script>

<template>
    <div class="row justify-content-center ">
        <div class="col-4">
            <div class="form-control text-center bg-light">
                <span>Resultado</span>
            </div>
        </div>
        <div class="col-8 ps-4">
            <span class="form-control text-center bg-light">{{ props.filtraOperacao }}</span>
        </div>
    </div>
</template>