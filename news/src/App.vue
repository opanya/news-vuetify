<template>
  <v-app>
    <v-app-bar color="blue darken" dark app>
      <v-app-bar-nav-icon v-on:click="navigation = !navigation"></v-app-bar-nav-icon>
      <v-toolbar-title>
        Новости
      </v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="navigation" absolute temporary>
    </v-navigation-drawer>
    <v-main>
      <v-card>
        <v-img src="https://picsum.photos/500" class="white--text align-end"
          gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)" height="200px">
          <v-card-title v-text="87464867"></v-card-title>
        </v-img>
      <v-card-text>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Necessitatibus, praesentium iusto aliquam ullam similique provident totam optio consectetur quis? Quibusdam tempora debitis veniam id sed recusandae beatae minus vitae quod.
        </p>
      </v-card-text>
      
        <v-card-actions>
          <v-spacer></v-spacer>
      
          <v-btn icon>
            <v-icon>mdi-heart</v-icon>
          </v-btn>
      
          <v-btn icon>
            <v-icon>mdi-bookmark</v-icon>
          </v-btn>
      
          <v-btn icon>
            <v-icon>mdi-share-variant</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data: () => ({
    navigation: false
  }),
};
</script>
