<template>
    <!--  сколько колонок из 12 будет занимать  -->
    <v-col cols="4">
        <v-card @click="openPhoto">
            <v-card-title>{{ photo.title }}</v-card-title>
            <v-card-text>
                <v-img 
                width="200"
                height="200"
                :src="photo.url"
                />
            </v-card-text>
        </v-card>
        <!-- {{ photo.id + photo.title }} -->
    </v-col>
</template>

<script>
import {mapMutations} from 'vuex'

export default {
    props: {
        photo: {
            type: Object,
            require: true
        }
    },
    methods: {
        ...mapmutations(["setCurrentPhoto", "showDialog", "hideDialog"]),
        openPhoto() {
            // this.$emit('openPhoto', this.photo)
            this.setCurrentphoto( this.photo)
            this.showDialog()
        }
    }
}
</script>

<style>
    
</style>