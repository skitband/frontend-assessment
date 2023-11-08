<style>
    @import 'bootstrap/dist/css/bootstrap.min.css';
    @import './style.css';
</style>

<script setup>
    import HeaderComponent from './components/HeaderComponent.vue'
    import CardComponent from './components/CardComponent.vue'

    const data = [
        {
            cardText: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies, purus lectus malesuada libero, sit amet commodo magna eros quis urna.',
            imgSrc: 'https://via.placeholder.com/400x300',
        },
        {
            cardText: 'Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Maecenas porttitor congue massa. Fusce posuere, magna sed pulvinar ultricies.',
            imgSrc: 'https://via.placeholder.com/400x300',
        },
        {
            cardText: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut non purus quis urna aliquet tempor. Morbi lacinia, diam fringilla dapibus iaculis, nisl ipsum elementum lorem, eget porttitor. . Morbi lacinia, diam fringilla dapibus iaculis, nisl ipsum elementum lorem, eget porttitor.',
            imgSrc: 'https://via.placeholder.com/400x300',
        },
    ];

</script>

<template>
    <HeaderComponent msg="Hello Developers!" />
    <main>
      <CardComponent :cardData="data" />
    </main>
</template>


