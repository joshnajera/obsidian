Different than what's used in vuejs

```html
<template>

  <ion-app><!-- Important wrapper -->

    <ion-router-outlet /><!-- Get's replaced with actual content via router -->

  </ion-app>

</template>

  

<script setup lang="ts">

import { IonApp, IonRouterOutlet } from '@ionic/vue';

</script>
```