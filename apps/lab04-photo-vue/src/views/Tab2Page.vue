<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Photo Gallery</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <!-- iOS Large Title -->
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Photo Gallery</ion-title>
        </ion-toolbar>
        <ion-toolbar>
          <ion-text class="ion-padding">
            โดย นางสาวดวงฤทัย อัปกาญจน์<br />
            รหัสนักศึกษา 663380014-2
          </ion-text>
        </ion-toolbar>
      </ion-header>

      <!-- Photo Grid -->
      <ion-grid>
        <ion-row>
          <ion-col
            size="6"
            v-for="photo in photos"
            :key="photo.filepath"
          >
            <ion-img :src="photo.webviewPath" />
          </ion-col>
        </ion-row>
      </ion-grid>

      <!-- Floating Action Button -->
      <ion-fab vertical="bottom" horizontal="center" slot="fixed">
        <ion-fab-button @click="addNewToGallery">
          <ion-icon :icon="camera" />
        </ion-fab-button>
      </ion-fab>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { camera } from 'ionicons/icons'
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonGrid,
  IonRow,
  IonCol,
  IonImg,
  IonFab,
  IonFabButton,
  IonIcon,
  IonText
} from '@ionic/vue'

import { usePhotoGallery } from '@/composables/usePhotoGallery'

const { photos, addNewToGallery } = usePhotoGallery()
</script>
