<template>
    <div>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Application
          </v-list-item-title>
          <v-list-item-stitle>
            Subtext
          </v-list-item-stitle>
        </v-list-item-content>
      </v-list-item>
      <v-list>
          <v-list-group v-for="(item, i) in items" :key="i" v-model="item.active" :prepend-icon="item.icon" no-action="">
            <template v-slot:activator>
                <v-list-tile-content>
                    <v-list-item-title v-text="item.title"></v-list-item-title>
                </v-list-tile-content>
                <v-spacer />
            </template>
            <v-list-item 
                v-for="subItem in item.subItems" 
                :key="subItem.title" 
                :to="subItem.to"
            >
                <v-list-item-content>
                    <v-list-item-title 
                        v-text="subItem.title"
                    ></v-list-item-title>
                </v-list-item-content>
            </v-list-item>
          </v-list-group>
      </v-list>
    </div>
</template>

<script>
export default {
    props: ["title"],
    data(){
        return {
            items: [
                {
                    title: 'home',
                    icon: 'mdi-home',
                    subItems: [
                        {
                            title: 'Dashboard',
                            to: '/'
                        }
                    ]
                },
                {
                    title: 'about',
                    icon: 'mdi-account',
                    subItems: [
                        {
                            title: 'About',
                            to: '/about'
                        }
                    ]
                }
            ]
        }
    }
}
</script>

