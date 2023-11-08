<style>
    @import 'bootstrap/dist/css/bootstrap.min.css';
    @import './style.css';
</style>

<script>
import data from "../../data.json";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainContent from "./components/MainContent.vue";

export default {
    name: "App",
    data() {
        return {
            items: data,
            activeTab: 1,
            isMobile: false,
            activeAccordion: 1,
        };
    },
    computed: {
        currentTab() {
            return this.items.find((item) => item.id === this.activeTab);
        },
    },
    created() {
        this.checkWindowSize();
        window.addEventListener("resize", this.checkWindowSize);
    },
    destroyed() {
        window.removeEventListener("resize", this.checkWindowSize);
    },
    methods: {
        checkWindowSize() {
            this.isMobile = window.innerWidth < 768;
        },
        toggleAccordion(itemId) {
            if (this.activeAccordion === itemId) {
                this.activeAccordion = null;
            }
            else {
                this.activeAccordion = itemId;
            }
        },
        handleTabSelected(tabId) {
            this.activeTab = tabId;
        },
        handleAccordionToggled(itemId) {
            if (this.activeAccordion === itemId) {
                this.activeAccordion = null;
            } else {
                this.activeAccordion = itemId;
            }
        },
    },
    components: { HeaderComponent, MainContent  }
};
</script>

<template>
    <div class="container">
        <HeaderComponent />
        <MainContent
            :items="items"
            :is-mobile="isMobile"
            :active-tab="activeTab"
            :active-accordion="activeAccordion"
            :current-tab="currentTab"
            @tab-selected="handleTabSelected"
            @accordion-toggled="handleAccordionToggled"
        />
      
    </div>
  </template>
  

  
  