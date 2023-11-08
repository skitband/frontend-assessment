<script setup>
  import { defineProps } from 'vue';

  const props = defineProps({
    cardData: {
      type: Array,
    },
  });
</script>

<template>
  <div class="album py-5">
    <div class="container">
      <div class="row justify-content-center g-4">
        <div v-for="(card, index) in props.cardData" :key="index" class="col-12 col-md-4 custom-card">
          <div class="custom-card__wrapper card shadow-sm">
            <img class="custom-card__image img p-3" :src="card.imgSrc" alt="card thumbnail" />
            <div class="custom-card__body card-body d-flex flex-column">
              <p class="custom-card__text card-text flex-grow-1">{{ card.cardText }}</p>
              <div class="custom-card__button mt-auto">
                <button type="button" class="custom-card__button btn btn-sm btn-outline-dark border-2 rounded-5">READ MORE</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
