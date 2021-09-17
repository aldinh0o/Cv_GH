<template>
  <v-card
    color="red darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Aldo Misael <span class="light-blue--text text--lighten-3">Suarez Santamaria</span>
        </h1>
        <span>
          Programador Junior
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'CONTACTO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'thealdinh0@gmail.com',
            },
            {
              name: 'Teléfono',
              icon: 'mdi-cellphone-android',
              text: '55 3883 6110',
            },
            {
              name: 'Ubicación',
              icon: 'mdi-map-marker',
              text: 'Álvaro Obregón, Ciudad de México',
            },
          ],
        },
        socials: {
          title: 'REDES SOCIALES',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/Aldinh0o',
              link: 'https://github.com/aldinh0o',
            },
            {
              icon: 'mdi-facebook-box',
              text: 'facebook.com/aldinho.suarez',
              link: 'https://www.facebook.com/aldinho.suarez/',
            },
            {
              icon: 'mdi-twitter',
              text: 'twitter.com/TheAldinh0',
              link: 'https://twitter.com/TheAldinh0',
            },
            {
              icon: 'mdi-instagram',
              text: 'instagram.com/Aldinh0_Suarez',
              link: 'https://www.instagram.com/aldinh0_suarez',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            {
              icon: 'mdi-google-controller',
              text: 'VideoJuegos',
            },
            {
              icon: 'mdi-guitar-pick-outline',
              text: 'Guitarra',
            },
            {
              icon: 'mdi-android-debug-bridge',
              text: 'Programar',
            },
            {
              icon: 'mdi-movie',
              text: 'Cineasta',
            },
            {
              icon: 'mdi-music',
              text: 'Musica',
            },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Libros',
            },
          ],
        },
        languages: {
          title: 'IDIOMAS',
          items: [
            {
              text : 'Español',
              value: 100,
            },
            {
              text : 'Inglés',
              value: 50,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
