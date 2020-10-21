<template>
  <div id="app">
    <Header/>
    <div class="board">
      <div class="lane">
       <h2 class="lane-title">Backlog</h2>
          
            <draggable v-for="card in cards.backlog" :key="card.id">
                <Card >
                  {{card.text}}
                </Card>
            </draggable >
          
      </div>
      <div class="lane">
        <h2 class="lane-title">Desenvolvimento</h2>
          
            <draggable  v-for="card in cards.dev" :key="card.id">
              <Card >
                {{card.text}}
              </Card>
            </draggable >
         
      </div>
      <div class="lane">
        <h2 class="lane-title">Testes</h2>
      
            <draggable  v-for="card in cards.testes" :key="card.id">
              <Card >
                {{card.text}}
              </Card>
            </draggable >
          
      </div>
      <div class="lane">
        <h2 class="lane-title">Fechados</h2>
        
            <draggable  v-for="card in cards.fechados" :key="card.id">             
                <Card >
                  {{card.text}}
                </Card>
            </draggable >
         
      </div>
    </div>
  </div>
</template>

<script>

import Header from './components/Header'
import Card from './components/Card'
import initialCards from './initialCards'
import draggable from 'vuedraggable'

export default {
  name: 'App',
  components: {
    Header,
    Card,
    draggable
   
  },
  data: () => ({

      cards:{
        backlog: initialCards.backlog, 
        dev: initialCards.dev,
        testes: initialCards.testes,
        fechados:[]
      }
  })
}

</script>

<style>
.board{
  display: flex;
  justify-content: flex-start;
  margin: 1.2rem .8rem;
      }
.lane {
  background: var(--color-grey);
  width: 23rem;
  height: 30rem;
  border-radius: 0.8rem;
  box-shadow: 0 .1rem .2rem 0 rgba(33, 33, 33, .1);
  margin: 0 .8rem;
  padding: 0 0.7rem;
      }
.lane-title{
  padding: 0.8rem 0.5rem;
  margin-bottom: 0.6rem;
          }
</style>
