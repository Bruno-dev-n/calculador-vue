<template>
    <input class="rounded-pill text-center bg-warning" 
    type="number"
    :value="value"
        @input="$emit('update:value', $event.target.value)">
</template>

<script>
export default {
    props: ['value']
};
</script>