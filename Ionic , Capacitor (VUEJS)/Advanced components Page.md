```html

<script setup>
	import { IonPage, IonHeader, IonTitle, IonContent, IonToolbar } from '@ionic/vue'; 	

	import {IonList, IonItem, IonBackButton, IonButton, IonButtons} from '@ionic/vue';
	 import {add} from 'ionicons/icons'; // Access icon library
</script>

<template>
	<ion-page> <!-- Wraps everything  -->
		<ion-header>
			<ion-toolbar> <!-- for proper styling? -->
				<ion-buttons slot="start"> <!-- some components have default slots, this is one of them -->
					<ion-back-button default-href="/someDefaultPage">
					<!-- set default, bc on refresh we lose back data -->
					</ion-back-button>
					<ion-button>
						<ion-icon icon={add} slot="end"/>
					<ion-button>
				</ion-buttons>
				<ion-title>
					Some Title
				</ion-title>
			</ion-toolbar>
		</ion-header>
		<ion-content scrollY={false}> <!-- disable scrolling on mobile -->
			<!-- Lists -->
			<ion-list>
				<ion-item router-link='/someLink'> 
				<!--  -->
					1
				</ion-item>
				<ion-item>
					2
				</ion-item>
				<ion-item>
					3
				</ion-item>
			</ion-list>
		</ion-content>
		
		
	</ion-page>
</template>

<style scoped>
</style>
```