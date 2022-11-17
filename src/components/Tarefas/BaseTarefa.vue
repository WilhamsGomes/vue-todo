<template>
    <div>
        <v-list-item 
          :class="{'light-blue lighten-5 text-decoration-line-through':tarefa.concluido}" 
          @click="changeValue()"
        >
              <template>
                <v-list-item-action>
                  <v-checkbox :input-value="tarefa.concluido"></v-checkbox>
                </v-list-item-action>

                <v-list-item-content>
                  <v-list-item-title>{{tarefa.titulo}}</v-list-item-title>
                </v-list-item-content>
              </template>
        </v-list-item>  
    </div>
</template>

<script>
    export default {
        name:"BaseTarefa",
        props:['tarefa'],
        data(){
          return{
            tarefaR: this.tarefa
          }
        },

        methods: {

          changeValue(){
            this.tarefaR.concluido = !this.tarefaR.concluido
          }

        } 
    }
</script>

<style>

</style>