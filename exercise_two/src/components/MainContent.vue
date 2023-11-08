<template>
    <div class="main-content">
        <div v-if="isMobile">
            <div class="accordion">
                <div
                v-for="item in items"
                :key="item.id"
                :class="['accordion-item', { 'active': activeAccordion === item.id }]"
                >
                    <h2 class="accordion-header">
                        <button
                            :class="['accordion-button', { 'collapsed': activeAccordion !== item.id }]"
                            type="button"
                            @click="toggleAccordion(item.id)"
                            >
                            {{ item.title }}
                        </button>
                    </h2>
                    <div
                        :class="['accordion-collapse collapse', { 'show': activeAccordion === item.id }]"
                    >
                        <div class="accordion-body p-4 p-md-5 bg-body-secondary" v-html="item.content"></div>
                    </div>
                </div>
            </div>
        </div>
      <div v-else>
        <div class="nav-scroller p-1 mb-3 border-bottom">
          <nav class="nav nav-pills nav-fill nav-justified custom-pills bg-light-subtle">
            <a
              v-for="item in items"
              :key="item.id"
              :class="['nav-item', 'nav-link', 'link-body-emphasis', { active: activeTab === item.id }]"
              @click="selectTab(item)"
              href="#"
            >
              {{ item.title }}
            </a>
          </nav>
        </div>
      </div>
  
      <main class="container" v-if="!isMobile">
        <div v-if="currentTab" class="p-4 p-md-5 mb-4 rounded text-body-emphasis bg-body-secondary">
          <div class="col-12 px-0">
            <h1 v-if="currentTab">{{ currentTab.title }}</h1>
            <div v-if="currentTab" v-html="currentTab.content" class="lead my-3"></div>
          </div>
        </div>
      </main>
    </div>
</template>
  
<script>
    export default {
        props: {
            items: Array,
            isMobile: Boolean,
            activeTab: Number,
            activeAccordion: Number,
            currentTab: Object,
        },
        methods: {
            selectTab(item) {
                this.$emit("tab-selected", item.id);
            },
            toggleAccordion(itemId) {
                this.$emit("accordion-toggled", itemId);
            },
        }
    };
</script>
  