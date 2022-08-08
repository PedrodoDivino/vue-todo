<template>
  <div>
    <v-col cols="12" sm="6">
      <v-text-field
        v-model="InputSize"
        label="Your Task Here"
        outlined
        clearable
        @keyup.enter="AddTask"
      ></v-text-field>
    </v-col>
    <v-list flat subheader>
      <v-list-item-group v-model="settings" multiple active-class="">
        <div v-for="(task, index) in tasks" :key="index">
          <Task :task="task" />
        </div>
      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
import Task from "@/components/Tarefas/Task.vue";
export default {
  name: "Tasks",
  components: {
    Task,
    Task,
  },
  data() {
    return {
      InputSize: null,
      tasks: [{ title: "Ir ao mercado", concluded: false }],
    };
  },
  methods:{
AddTask(){
  if(this.InputSize){
    this.tasks.push({title:this.InputSize,
    concluded:false
    })
    this.InputSize= null
  }
}
  },
};
</script>
