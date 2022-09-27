<template>
  <div class="about">
    <v-container class="pa-6 mx-auto text-center" fluid>
      <h1>About Page</h1>
      <v-row>
        <v-col class="d-flex align-center"
        col="12"
        sm="6"><p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo iusto excepturi dolore asperiores ut voluptate quasi cum optio nemo est tempore voluptatum suscipit natus molestias, dolorum, doloremque facere aut tempora voluptatibus, officia minima quos. Eos nesciunt ratione voluptate et laboriosam cupiditate amet. Incidunt maxime ipsam nam corrupti neque quia aperiam corporis! Dicta iure veniam tempora, nulla ducimus neque, et eum perspiciatis in, modi fugiat! Ex expedita in repellendus eligendi architecto laboriosam vitae? At, provident delectus. Nulla a quas tempore maiores dolores? Optio, vel obcaecati? Enim ex voluptas suscipit consequatur quisquam nemo consequuntur nisi explicabo, ducimus sit iure soluta quibusdam nihil?
    </p>
      </v-col>
      <v-col 
      v-for="n in 1"
      :key="n"
      class="d-flex"
        col="4"
        sm="6">
        <v-img
        :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
        :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
        aspect-ratio="1"
      ></v-img>
      </v-col>
      </v-row>
    </v-container>
  </div>
</template>
