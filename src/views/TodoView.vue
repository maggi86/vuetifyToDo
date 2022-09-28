<template>
   <div
   class="home" max-width="700">
   <v-text-field
   v-model="newTaskTitle"
   @click:append="addTask"
   @keyup.enter="addTask"
   class="pa-2 mx-2"
   outlined
   append-icon="mdi-plus-circle-outline"
   color="purple accent-3"
   label="Add To Do List"
   hide-details
   clearable
   ></v-text-field>
   <v-list
   class="pt-0" flat>
        <!-- <template v-for="(item, index) in items"> -->
            <div
          v-for="task in tasks"
          :key="task.id"> 
          <v-list-item 
          @click="doneTask(task.id)"
          :class="{'pink lighten-4': task.done }">
            <template v-slot:default>
                <v-list-item-action>
                    <v-checkbox
                    :input-value="active"
                    color="purple accent-3">
                </v-checkbox>
                </v-list-item-action>

              <v-list-item-content>
                <v-list-item-title
                :class="{'text-decoration-line-through': task.done}"
                >{{task.headline}}</v-list-item-title>
              </v-list-item-content>             
              <v-list-item-action>
                  <v-btn
                  @click.stop="deleteTask(task.id)" 
                  icon>
                      <v-icon color="purple accent-3">mdi-delete-outline</v-icon>
                  </v-btn>
              </v-list-item-action>
            </template>
        </v-list-item>
        <v-divider
        class="mx-5"
          ></v-divider>
</div>
          
    </v-list>
</div> 
</template>
<script>
    export default{
        data() {
      return{
        newTaskTitle:'',
        tasks:[
            // {
            //     id:1,
            //     headline: 'Go to Gym',
            //     done: false
            // },
            // {
            //     id:2,
            //     headline: 'take children to park',
            //     done: false
            // },
            // {
            //     id:3,
            //     headline: 'walk my goldfish',
            //     done: false
            // },

        ]
    }},
    methods: {
        addTask(){
           let newTask = {
            id: Date.now(),
            headline: this.newTaskTitle,
            done: false
           }
           this.tasks.push(newTask)
           this.newTaskTitle =''
        },
        doneTask(id){
           let task = this.tasks.filter(task => task.id === id) [0]
           task.done = !task.done
        },
        deleteTask(id){
            this.tasks  = this.tasks.filter(task => task.id !== id)
        }
    }
}
</script>