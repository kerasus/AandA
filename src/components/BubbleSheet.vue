<template>
  <div class="bubble-sheet fit">
    <q-scroll-area class="fit">
      <div class="row header-labels shadow-2">
        <div class="col table-label">
          شماره سوال
        </div>
        <div v-for="(question, questionIndex) in choiceNumber" :key="questionIndex" class="col table-label">
          {{ questionIndex + 1 }}
        </div>
        <div class="col table-label">
          بی پاسخ
        </div>
      </div>
      <div v-for="(question, questionIndex) in choices" :key="questionIndex" class="row">
        <div class="col table-label">
          {{ questionIndex + 1 }}
        </div>
        <div v-for="(choiceItem, choiceItemIndex) in choiceNumber" :key="choiceItemIndex" class="col text-center">
          <q-item tag="label" v-ripple>
            <q-radio v-model="choices[questionIndex]" :val="(choiceItemIndex + 1)" />
          </q-item>
        </div>
        <div class="col text-center">
          <q-item tag="label" v-ripple>
            <q-radio v-model="choices[questionIndex]" :val="(choiceNumber + 1)" />
          </q-item>
        </div>
      </div>
      <div class="text-center">
        {{ userAnswer }}
      </div>
    </q-scroll-area>
  </div>
</template>

<script>
export default {
  name: "BubbleSheet",
  computed: {
    userAnswer () {
      return this.choices.join('')
    }
  },
  data() {
    return {
      choices: [],
      choiceNumber: 4,
      questionNumber: 100,
    }
  },
  created() {
    for (let i = 0; i < this.questionNumber; i++) {
      this.choices.push(null)
    }
  }
}
</script>

<style scoped lang="scss">
.bubble-sheet {
  .q-item {
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .header-labels {
    position: -webkit-sticky; /* Safari */
    position: sticky;
    top: 0;
    background-color: white;
    z-index: 1;
    height: 50px;
  }
  .table-label {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
}
</style>
