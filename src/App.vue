<template>
  <div class="main-container">
    <page-header></page-header>
    <page-main></page-main>
    <PageFooter></PageFooter>
  </div>
</template>

<script>
import { store } from './store';

import { inventory } from './data/inventory';
import PageHeader from './components/PageHeader.vue'
import PageMain from './components/PageMain.vue'
import PageFooter from './components/PageFooter.vue'

export default {

  data () {
    return {
      inventoryData: inventory,
      currentInventory: inventory,
      sectionType: store.state.sectionType,
      invType: store.state.invType,
    }
  },
  name: 'app',
  components: {
    PageHeader,
    PageMain,
    PageFooter,
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #efeade;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 16px;
}

h2,
p {
  margin-bottom: 15px;
}

h1 {
  font-size: 1.65rem;
  margin-bottom: 20px;
  text-align: center;
}

h2 {
  font-size: 1.25rem;
}

ul {
  list-style: none;
}

dl {
  margin-bottom: 15px;
}
 dt {
   font-weight: bold;
   margin-bottom: 5px;
 }

 dd {
   padding-left: 10px;
 }


header p {
  font-size: 1.3rem;
  margin-bottom: 5px;
  padding: 3px 0;
  text-align: center;
}

header .inner-container {
  max-width: 450px;
}

nav {
  padding: 0 10px;
}

nav ul {
  display: grid;
  gap: 3px;
  grid-template-columns: repeat(5, 1fr);
  margin-bottom: 10px;
  padding: 0;
  text-align: center;
  width: 100%;
}

main {
  display: flex;
  flex-flow: column;
  justify-content: center;

  flex: 1 0;
}

main .inner-container {
  flex: 0 0;
}

main,
footer {
  padding: 10px;
}

header,
footer {
  color: #efeade;
  background: #111314;
}

footer {
  height: 40px;
  text-align: center;
}

button,
nav button {
  border: none;
  border-radius: 5px;
  display: inline-block;
  font-size: 1rem;
  margin: 2px 4px 5px;
  min-width: 75px;
  padding: 5px 10px;
}

button {
  background: #992f23;
  color: #efeade;
}

nav button {
  background: transparent;
  color: #898991;
  font-size: 1.1rem;
  margin: 0;
  min-width: 65px;
  padding: 6px 6px;
}

nav button.active {
  color: #992f23;
}

button:hover {
  background: #ad584f;
  color: #fff;
  cursor: pointer;
}

nav button:hover {
  background: transparent;
  color: #efeade;
}

.main-container {
  display: flex;
  flex-flow: column nowrap;

  min-height: 100vh;
  margin: 0 auto;
}

.inner-container {
  margin-left: auto;
  margin-right: auto;
  max-width: 600px;
}

/***** task styles *****/
.word-box,
.prefix-box,
.answer-buttons-box,
.answer-box {
  border-radius: 5px;
  font-size: 1.125rem;
  margin: 0 auto 15px;
  text-align: center;
  width: 300px;
}

.word-box,
.answer-box {
  display: flex;
  justify-content: center;
  flex-flow: column nowrap;

  height: 70px;
  line-height: 25px;
}

.word-box {
  background: rgba(49, 36, 80, .04);
  margin: 0 auto 20px;
  max-width: 400px;
  text-align: center;
}

.word-box p {
  font-style: italic;
  font-weight: 700;
  margin-bottom: 0;
}

.word-box__prefix {
  border-bottom: 2px dashed #888;
  width: 50px;
}

.word-box__word {
  border-bottom: 2px dashed transparent;
}

.prefix-box {
  margin-bottom: 15px;
  text-align: center;
}

.answer-box__text {
  margin-bottom: 5px;
}

.answer-box__answer {
  font-weight: bold;
  margin-bottom: 0;
}

.answer-box.answer-correct {
  background: #D4EDDA;
}

.answer-box.answer-incorrect {
  background: #F8D7DA;
}
/**** end taks styles *****/


/***** Final box styles *****/
.final-box {
  max-width: 400px;
}

.final-box li {
  padding: 4px;
}

.final-box li:nth-child(odd) {
  background: lightgrey;
  border-radius: 4px;
}


/***** buttons *****/
.hero-buttons {
  text-align: center;
  min-width: 300px;
}

.hero-buttons button {
  background: transparent;
  border: 1px dashed #992f23;
  color: #992f23;
}

.hero-buttons button:hover {
  background: #992f23;
  border-color: #992f23;
  color: #efeade;
}

.btn-check {
  width: 100px;
}
/***** end buttons *****/

/**** Misc styles *****/
.center-text {
  text-align: center;
}


@media (min-width: 544px) {
  h2,
  p {
    margin-bottom: 25px;
  }

  h1 {
    font-size: 2rem;
    margin-bottom: 30px;
  }
  
  h2 {
    font-size: 1.375rem;
  }

  header p {
    font-size: 1.4rem;
    margin-bottom: 15px;
  }

  nav {
    margin-bottom: 15px;
  }

  button {
    font-size: 1.1rem;
    margin: 2px 6px;
    padding: 5px 10px;
  }

  nav button {
    font-size: 1.2rem;
    margin: 0;
    min-width: 80px;
    padding: 8px 12px;
  }

  .hero-buttons button {
    margin-bottom: 15px;
    min-width: 170px;
  }

  .word-box,
  .articles-box,
  .check-answer-box,
  .answer-box {
    font-size: 1.25rem;
    margin-bottom: 25px;
    width: 300px;
  }

  .word-box,
  .answer-box {
    height: 90px;
  }

  .word-box p {
    margin-bottom: 10px;
  }

  .answer-box__text {
    margin-bottom: 10px;
  }
}

@media (min-width: 940px), (orientation: portrait) and (min-width: 544px) {
  h2,
  p {
    margin-bottom: 25px;
  }

  h1 {
    font-size: 2.5rem;
  }
  
  h2 {
    font-size: 2rem;
  }

  button {
    font-size: 1.2rem;
    margin: 2px 6px;
    min-width: 80px;
    padding: 6px 10px;
  }

  .hero-buttons button {
    min-width: 180px;
  }

  .word-box,
  .articles-box,
  .check-answer-box,
  .answer-box {
    margin-bottom: 30px;
  }
}
</style>
