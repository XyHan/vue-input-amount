<script>
import InputAmount from '../components/InputAmount.vue';

export default {
  name: 'HomeView',
  components: { InputAmount },
  data() {
    return {
      amount: '1337',
      locale: 'fr-FR',
      currency: 'EUR'
    }
  }
}

</script>

<template>
  <main>
    <h1>Input amount with formatted amount</h1>
    <input-amount v-model="amount" :currency="currency" :locale="locale" />
    <span>{{ amount }}</span>
  </main>
</template>
