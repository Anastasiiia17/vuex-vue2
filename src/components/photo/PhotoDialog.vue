<template>
     <v-dialog
        v-model="$store.state.dialogVisible"
        max-width="500"
        @click:outside="$store.commit('hideDialog')"
      >
      <v-card>
          <v-card-title>{{ full_title }}</v-card-title>
          <v-card-text>
              <v-img 
              :src="$store.getters.getCurrentPhoto.url"
              />
          </v-card-text>
      </v-card>
  
      </v-dialog>
</template>
<script>
export default {
    // props: {
    //    photo: {
    //        type: Object,
    //        required: true 
    //    },
    //     value: {
    //        type: Boolean,
    //        default: false,
    //     }
    // },
    // created(){
    //     this.dialogVisible = this.value
    // },
    // data: () => ({
    //    dialogVisible: false
    // }),
    // watch: {
    //     value(newValue){
    //         this.dialogVisible = newValue
    //     },
    //     dialogVisible(newValue) {
    //         this.$emit('input', newValue)
    //     }
    // },
    computed: {
        full_title() {
            return `Название фотографии - ${this.$store.getters.computed.title}`
        }
    }


}
</script>


<style >
    
</style>