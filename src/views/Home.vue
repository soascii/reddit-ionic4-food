<template>

  <ion-card>

    <ion-item>
      
      <ion-label position="floating">
        Insert text:
      </ion-label>

      <ion-input :value="greeting" @input="greeting = $event.target.value">
      </ion-input>

    </ion-item>

    <ion-button color="tertiary" expand="full" @click="handleClick()">
      Press me
    </ion-button>

  </ion-card>

  
</template>

<script>
export default {

  data(){
    return{
      greeting: ''
    }
  },

  methods:{

    async handleClick(){

     const alert= await this.$ionic.alertController.create({
        header: 'Alerta',
        subHeader: 'Subtitulo',
        message: this.greeting,
        buttons:['Ok']

      })
      alert.present()

      //  .then(a => a.present())
    }
  }
  
}
</script>
