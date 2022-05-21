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
    <header class="main-header">
      <h2>vue-input-amount</h2>
      <a href="https://github.com/XyHan/vue-input-amount">GitHub</a>
    </header>
    <section class="main-wrapper">
      <article>
        <input-amount v-model="amount" :currency="currency" :locale="locale" class="input-amount" />
        <footer>
          <span>Parent's model value:</span>
          <span>{{ amount }}</span>
        </footer>
      </article>
    </section>
  </main>
</template>

<style>
  html, body {
    padding: 0;
    margin: 0;
    font-family: Roboto, Arial, sans-serif;
    background-color: #F4F4F4;
  }
  .main-header {
    height: 30vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 10px;
    border-bottom: 1px solid black;
    background: rgba(69, 239, 194, 1.0);
    background: -webkit-linear-gradient(bottom right, rgba(69, 239, 194, 1.0), rgba(109, 30, 57, 1.0));
    background: -moz-linear-gradient(bottom right, rgba(69, 239, 194, 1.0), rgba(109, 30, 57, 1.0));
    background: linear-gradient(to top left, rgba(69, 239, 194, 1.0), rgba(109, 30, 57, 1.0));
  }
  .main-header > h2 {
    color: #F4F4F4;
    text-shadow: 1px 1px #3F3F3F;
  }
  .main-header > a {
    text-decoration: none;
    width: 100px;
    border: 1px solid #F4F4F4;
    border-radius: 5px;
    text-align: center;
    padding: 10px;
    color: #F4F4F4;
    transition: 0.3s;
  }
  .main-header > a:hover {
    background-color: #F4F4F4;
    border: 1px solid #569587;
    color: #569587;
  }
  .main-wrapper {
    width: 100%;
    padding-top: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .main-wrapper > article {
    width: 300px;
    background-color: #FFFFFF;
    box-shadow: 0 8px 8px -5px rgba(255,255,255,0.75);
    -webkit-box-shadow: 0 8px 8px -5px rgba(255,255,255,0.75);
    -moz-box-shadow: 0 8px 8px -5px rgba(255,255,255,0.75);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding: 15px 0;
  }
  .input-amount {
    width: 90%;
    height: 40px;
    text-align: center;
    border: 2px solid #F4F4F4;
  }
  .main-wrapper > article > footer {
    width: 90%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
  }
  .main-wrapper > article > footer > span {
    overflow: hidden;
    text-overflow: ellipsis;
  }
</style>
