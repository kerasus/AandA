<template>
  <q-page class="participate-page">
    <q-linear-progress class="timer" color="positive" :value="0.3" />
    <q-img
      src="http://www.matiaan.com/app/upload_files/mobtakerangirl/img/pic_of_quiz/673dadc979f2c8ed0457f3c2887dc8be.jpg"
      spinner-color="primary"
      class="full-width"
    />
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex'
})
</script>

<style scoped lang="scss">
.participate-page {
  .timer {
    position: -webkit-sticky; /* Safari */
    position: sticky;
    top: 50px;
    z-index: 1;
  }
}
</style>
