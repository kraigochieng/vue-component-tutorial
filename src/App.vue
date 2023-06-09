<template>
  <h1>Props</h1>
  <GreetingMessage name="Kraig"/>
  <GreetingMessage :name="name"/>
  <ArticlePage title="bananas" :likes="4" :isPublished="true"/>

  <h1>Provide/Inject</h1>
  <p>App username {{ name }}</p>
  <ComponentC />
  <h1>Component Events</h1>
  <button @click="showPopup = true">Open Popup</button>
  <PopupComponent v-show="showPopup" @closePopup="closePopup"/>
  <OrderComponent v-for="(order, index) in orders" :key="index" :id="order.id" :telephone_number="order.telephone_number" :description="order.description"></OrderComponent>
</template>

<script>
// Components
import GreetingMessage from './components/GreetingMessage.vue';
import ArticlePage from './components/ArticlePage.vue';
import ComponentC from './components/ComponentC.vue';
import PopupComponent from './components/PopupComponent.vue';
import OrderComponent from './components/OrderComponent.vue';

export default {
    name: "App",

    components: {
      GreetingMessage,
      ArticlePage,
      ComponentC,
      PopupComponent,
      OrderComponent
    },

    data: function() {
      return {
        name: 'Omondi',

        showPopup: false,

        orders: [{
          id: '1',
          telephone_number: 'Kraig',
          description: 'Ochieng',
        },

        {
          id: '2',
          telephone_number: '083662382',
          description: 'Omondi',
        }
      ]
      }
    },

    methods: {
      closePopup(name) {
        this.showPopup = false
        console.log(name)
      },
    },

    provide() {
      return {
        username: this.name,
      }
    },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
