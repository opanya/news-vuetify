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
    <v-main app>
       <v-container class="grey lighten-5">
      <v-row
        no-gutters
        style="height: 150px;"
      >
        <v-col
          v-for="(item,i) in news" v-bind:key = "i"
        >
    
      <v-card>
        <v-img v-bind:src="item.urlToImage" class="white--text align-end"
          gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)" height="200px">
          <v-card-title v-text=item.title></v-card-title>
        </v-img>
      <v-card-text>
        <p>
          {{ item.description }}
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
      
          <v-btn plain color="deep-purple" :href = "item.url" target = "_blank">
            <v-icon>mdi-share-variant</v-icon> Читать полностью
          </v-btn>
        </v-card-actions>
      </v-card>
     </v-col> 
    </v-row>
    </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {
  },

  data: () => ({
    navigation: false,
    news :[]
  }),
  methods: {
    getNews(){
      this.axios({
        method : 'GET',
        url: "https://newsapi.org/v2/top-headlines?country=us&apiKey=d7f41a32c26b4bbfb596d58b1a54c766"
      }).then((response) =>{
        this.news = response.data.articles;
      })
    }
  },
  mounted() {
    this.getNews();
  },
};
</script>
