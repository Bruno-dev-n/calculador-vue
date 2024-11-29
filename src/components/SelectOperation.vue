
<template>
    <select class="rounded-pill text-center bg-info" :value="value" @change="$emit('input', $event.target.value)">
        <option value="menos">-</option>
        <option value="mais">+</option>
        <option value="vezes">*</option>
        <option value="dividir">/</option>
    </select>
</template>
    <script>
    export default {
        props: ['value']
    };
    </script>