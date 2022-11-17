<template>
    <div>
        <v-col cols="12">
            <v-text-field
              v-model="campoInput"
              label="Qual sua tarefa?"
              outlined
              clearable
              @keyup.enter="handleAddTarefa()"
            >
            </v-text-field>
        </v-col>

        <v-list flat subheader >
            <v-list-item-group
              multiple
              active-class=""
            >
            <div
              v-for="(tarefa, index) in tarefas" :key="index"
            >
              <BaseTarefa
                :tarefa="tarefa"
              />        
            </div>
            </v-list-item-group>
        </v-list>
    </div>
</template>

<script>
  import BaseTarefa from '@/components/Tarefas/BaseTarefa.vue';

  export default {
    name: "HomeView",
    components: { 
      BaseTarefa 
    },
    data(){
      return{
        campoInput:null,
        tarefas: [
          {titulo: "Ir ao mercado", concluido: false},
          {titulo: "Assistir aula", concluido: true},
          {titulo: "Farmácia", concluido: true},
        ],
      }
    },
      methods:{
        handleAddTarefa(){
            if(this.campoInput){
              this.tarefas.push({
                titulo:this.campoInput,
                concluido: false
              })
              this.campoInput = null
            }
        }
    },
}
</script>
