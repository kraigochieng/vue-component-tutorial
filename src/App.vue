<template>
  <!--Props-->
    <h1>Props</h1>
    <GreetingMessage name="Kraig"/>
    <GreetingMessage :name="name"/>
    <ArticlePage title="bananas" :likes="4" :isPublished="true"/>

    <!--Provide/Inject-->
    <h1>Provide/Inject</h1>
    <p>App username {{ name }}</p>
    <ComponentC />

    <!--Component Events-->
    <h1>Component Events</h1>
    <button @click="showPopup = true">Open Popup</button>
    <PopupComponent v-show="showPopup" @closePopup="closePopup"/>
    <OrderComponent v-for="(order, index) in orders" :key="index" :id="order.id" :telephone_number="order.telephone_number" :description="order.description"></OrderComponent>
    <InputComponent v-model="name"/>

    <!--Slots-->
    <h1>Slots</h1>
    <CardComponent></CardComponent>
    <CardComponent><h1>Content 1</h1></CardComponent>
    <CardComponent><h2>Content 2</h2></CardComponent>
    <CardComponent><InputComponent/></CardComponent>

    <CardComponent>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template  v-slot:footer>
        <h3>Footer</h3>
      </template>
    </CardComponent>

    <NamesComponent>
      <template v-slot:first_name="prop">
        {{ prop.first_name }},
      </template> 
      <template v-slot:last_name="props">
        {{ props.last_name }}
      </template>
    </NamesComponent>
    <h4>App Styles</h4>
    <ChildStyles>
      <h4>Child Styles</h4>
    </ChildStyles>

    <!--Dynamic Components-->
    <h1>Dynamic Components</h1>
    <button @click="activeTab = 'TabAComponent'">Tab A</button>
    <button @click="activeTab = 'TabBComponent'">Tab B</button>
    <button @click="activeTab = 'TabCComponent'">Tab C</button>
    <!--Maintain Data In Dynamic Components-->
    <keep-alive>
      <component :is="activeTab"/>
    </keep-alive>


    <!--Teleport Tag-->
    <h1>Teleport Tag</h1>
    <teleport to="#portal-root">
      <PortalComponent />
    </teleport>
</template>

<script>
// Components
import GreetingMessage from './components/GreetingMessage.vue';
import ArticlePage from './components/ArticlePage.vue';
import ComponentC from './components/ComponentC.vue';
import PopupComponent from './components/PopupComponent.vue';
import OrderComponent from './components/OrderComponent.vue';
import InputComponent from './components/InputComponent.vue';
import CardComponent from './components/CardComponent.vue';
import NamesComponent from './components/NamesComponent.vue'
import ChildStyles from './components/ChildStyles.vue'
import TabAComponent from './components/TabAComponent.vue'
import TabBComponent from './components/TabBComponent.vue'
import TabCComponent from './components/TabCComponent.vue'
import PortalComponent from './components/PortalComponent.vue'

export default {
    name: "App",

    components: {
    GreetingMessage,
    ArticlePage,
    ComponentC,
    PopupComponent,
    OrderComponent,
    InputComponent,
    CardComponent,
    NamesComponent,
    ChildStyles,
    TabAComponent,
    TabBComponent,
    TabCComponent,
    PortalComponent,
},

    data: function() {
      return {
        name: 'Omondi',

        showPopup: false,

        orders: [{
          id: '1',
          telephone_number: '0793562565',
          description: '',
        },

        {
          id: '2',
          telephone_number: '0735276327',
          description: '',
        }
      ],

      activeTab: 'TabAComponent'
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

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

h4 {
  color: orange
}
</style>
