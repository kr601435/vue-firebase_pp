<template>
  <div>
    <v-list-group
        v-for="(item, index) in items"
        :key="index"
        v-model="item.active"
        :prepend-icon="item.icon"
        no-action
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="subItem in item.subItems"
          :key="subItem.title"
          :to="subItem.to"
        >
          <v-list-item-content>
            <v-list-item-title v-text="subItem.title"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
  </div>
</template>

<script>
export default {
  props: ['footer'],
  data () {
    return {
      items: [
        {
          title: 'home',
          icon: 'mdi-home',
          subItems: [
            {
              title: 'Dashboard',
              to: '/'
            },
            {
              title: 'About',
              to: '/about'
            }
          ]
        },
        {
          title: 'about',
          active: true,
          icon: 'mdi-account',
          subItems: [
            {
              title: 'xxx',
              to: '/xxx'
            }
          ]
        }
      ]
    }
  }
}
</script>
