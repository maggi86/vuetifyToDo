<template>
   <div
   class="home" max-width="700">
   <v-list flat>
        <!-- <template v-for="(item, index) in items"> -->
          <v-list-item
          v-for="task in tasks"
          :key="task.id">
            <template v-slot:default="{ active }">
                <v-list-item-action>
                    <v-checkbox
                    :input-value="active"
                    color="danger">
                </v-checkbox>
                </v-list-item-action>

              <v-list-item-content>
                <v-list-item-title
                >{{task.headline}}</v-list-item-title>
              </v-list-item-content>
              <v-divider
          ></v-divider>
            </template>
</v-list-item>
          
    </v-list>
</div> 
</template>
<script>
    export default{
        data() {
      return{
        tasks:[
            {
                id:1,
                headline: 'Go to Gym'
            },
            {
                id:2,
                headline: 'take children to park'
            },
            {
                id:3,
                headline: 'walk my goldfish'
            },

        ]
    }},
}
</script>