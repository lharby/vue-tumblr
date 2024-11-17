<script setup>
import { computed } from 'vue';

const props = defineProps({
    active: {
        type: Boolean,
        required: false
    }
})

const hanleCloseModal = computed(() => {
    return !props.active
})

</script>

<template>
    <div class="modal" :class="props.active ? 'modal--active' : ''">
        <button class="modal__close" :click="hanleCloseModal">
            <span class="hidden">CLOSE</span>
            {{ props.active }}
        </button>
        <div class="modal__content"></div>
    </div>
    <div class="modal__backdrop" :class="props.active ? 'modal__backdrop--active' : ''"></div>
</template>

<style lang="scss">
@use "sass:color";
@use '../../scss/functions/variables' as *;

.modal {
    position: fixed;
    background-color: transparentize($colour__white, 0.1);
    display: none;
    flex-direction: column;
    align-self: center;
    height: 50%;
    margin: 0 auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 50%;
    z-index: 1;

    &--active {
        display: flex;
    }

    &__backdrop {
        position: fixed;
        display: none;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 0;
        background-color: transparentize($colour__black, 0.2);


        &--active {
            display: block;
        }
    }
}
</style>