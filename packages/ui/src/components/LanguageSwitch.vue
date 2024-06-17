<template>
 <div>
   <v-btn
       id="menu-activator"
       color="primary"
   >
    {{$t('Language')}}
   </v-btn>

   <v-menu activator="#menu-activator">
     <v-list>
       <v-list-item
           v-for="(item, index) in items"
           :key="index"
           :value="index"
           @click="switchLanguage(item.lang)"
       >
         {{ item.title }}
       </v-list-item>
     </v-list>
   </v-menu>
 </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: 'English',lang:"en" },
      { title: '简体中文',lang:"zhCN" },
    ],
  }),
  methods: {
    switchLanguage(locale) {
      this.$i18n.locale = locale;
    },
  },
};
</script>
