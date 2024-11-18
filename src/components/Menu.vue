<!-- <script>

export default {
    data() {
        return {

        }
    },
    methods: {
        clickInItem() {
            console.group('Menu.vue');
            console.log('clickInItem');
            console.groupEnd('Menu.vue');
            this.$emit('clickInItem', 'Hello from child');
        }
    }
}

</script> -->

<script setup lang="ts">

const emit = defineEmits<{
    (event: 'clickInItem', message: string): void;
}>();


function clickInItem(): void {
    console.group('Menu.vue => clickInItem');
    console.log('clickInItem');
    console.groupEnd();
    emit('clickInItem', 'Hello from child');
}

</script>


<template>
    <section class="menu">
        <ul class="menu__list">
            <li class="menu__item" v-on:click="clickInItem">Item 1</li>
            <li class="menu__item">Item 2</li>
            <li class="menu__item">Item 3</li>
        </ul>
    </section>
</template>

<style scoped></style>