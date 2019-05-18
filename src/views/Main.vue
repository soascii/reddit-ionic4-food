<template>
    <div>
      
            <ion-card v-for="post in posts" :key="post.data.id" style="border: 1px solid white" >
                <ion-card-content>

                    <template v-if="post.data.thumbnail.startsWith('https://')">
                         <img :src="post.data.thumbnail">
                    </template>
      
                    <ion-label color="dark">{{post.data.title}}</ion-label>
               
              
                    <ion-button color="light" style="border-bottom: 1px solid blue" expand="full" @click="viewMore(post.data)">
                        View More
                    </ion-button>
                    
                   

                </ion-card-content>
            </ion-card>
       
    </div>
</template>

<script>
import axios from 'axios';
export default {

    data(){
        return{
            posts:[]
        }
    },

    async mounted(){
      const response =  await axios.get('https://www.reddit.com/r/recipes.json')
      this.posts = response.data.data.children;
    },
    methods:{
        viewMore(post){
                    this.$router.push({ name: 'detail', params:{ post }})
        }
    }
    
    }
    

</script>
