```html

<script setup>
	// 5 Essential components, which you need on every new "page" you want
	// Not necessarily every component
	import { IonPage, IonHeader, IonTitle, IonContent, IonToolbar } from '@ionic/vue'; 	
</script>

<template>
	<ion-page> <!-- Wraps everything  -->
		<ion-header>
			<ion-toolbar> <!-- for proper styling? -->
				<ion-title>
					Some Title
				</ion-title>
			</ion-toolbar>
		</ion-header>
		<ion-content>
			Some Content
		</ion-content>
		
		
	</ion-page>
</template>

<style scoped>
</style>
```