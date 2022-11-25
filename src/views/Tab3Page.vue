<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Button</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Button</ion-title>
        </ion-toolbar>
      </ion-header>
      
      <ExploreContainer name="Warning Button" />
      <ion-button color="danger" shape="round" @click="presentAlert">Warning Button</ion-button>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, alertController } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';

export default defineComponent({
  name: 'Tab3Page',
  components: { ExploreContainer, IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonButton },
  setup() {
      const presentAlert = async () => {
        const alert = await alertController.create({
          header: 'Alert',
          subHeader: 'Important message',
          message: 'Error: Peringatan! [041643527][Damelia]<br>VM: {"fullscreen":true}<br>Info: native event handler',
          buttons: ['OK'],
        });

        await alert.present();
      };

      return { presentAlert };
    },
});
</script>
