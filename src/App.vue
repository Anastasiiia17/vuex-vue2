<template>
   <v-app>
     <Navbar/>
     <PhotoForm v-if="photos.length < 11" @addPhoto="addPhoto"/>
     <div v-else>Вы не можете добавить больше фото</div>
     <!-- <router-view/> -->
    <v-row>
    <Photo
          v-for="photo in $store.getters.getAllPhotos"
          :photo="photo"
          />
     </v-row>
     <PhotoDialog /> 
     <!-- :photo="currentPhoto" v-model="dialogVisible" -->
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Photo from "@/components/photo/Photo.vue";
import PhotoForm from './components/PhotoForm.vue';
import PhotoDialog from "@/components/photo/PhotoDialog.vue";


export default {
  name: 'App',
  components: {
    Navbar,
    Photo,
    PhotoForm,
    PhotoDialog
  },
  data: () => ({
    photos: [
      // {id: 1, title: 'Фото 1'},
      // {id: 2, title: 'Фото 2'},
      // {id: 3, title: 'Фото 3'},
      // {id: 4, title: 'Фото 4'},
    ],
    // currentPhoto: null,
    // dialogVisible: false,
  }),
  mounted() {
    // this.fethTodo()
    this.$store.dispatch("fetchPhotos")
  },
  methods: {
    // fethTodo() {
    //    this.axios.get(`https://jsonplaceholder.typicode.com/photos?_limit=10`)
    //     .then(response => this.photos = response.data)
    // },
    addPhoto(photo) {
      this.photos.push(photo)
    },
    openPhoto(photo) {
      this.currentPhoto = photo
      this.dialogVisible = true
    }
  }
};
</script>
