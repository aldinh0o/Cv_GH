<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="PERFIL"
      >
        Soy un pasante de ingenería en el area de desarrollo software multiplataforma, me encantaría entrar a formar parte de una empresa en donde poder aplicar
        todos mis conocimientos y, al mismo tiempo, que me
        permita desarrollarme profesionalmente.
      </content-section>
      <content-section
        v-if="educations"
        title="Educación"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="prouds"
        title="Habilidades"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
              <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="proud.value"
                />
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Manejo de software"
      >
        <template slot="actions">
          (1/1)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-account-switch',
        text  : 'Trabajo en equipo',
        source: '',
        value : 95,
      },
      {
        icon  : 'mdi-palette',
        text  : 'Creatividad',
        source: '',
        value : 75,
      },
      {
        icon  : 'mdi-human-child',
        text  : 'Liderazgo',
        source: '',
        value : 70,
      },
      {
        icon  : 'mdi-radioactive',
        text  : 'Majeno de estrés',
        source: '',
        value : 90,
      },
    ],
    educations: [
      {
        from       : '2019',
        to         : 'En Curso',
        title      : 'Universidad Tecnológica Emiliano Zapata',
        location   : 'Emiliano Zapata, Morelos',
        description: 'Ingeneria Desarrollo Software Multiplataforma',
      },
    ],
    skills: [
      {
        title: 'VueJS Framework',
        icon : 'mdi-vuejs',
        value: 95,
      },
      {
        title: 'ReactJS & React-Native Framework',
        icon : 'mdi-laravel',
        value: 80,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 90,
      },
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 60,
      },
      {
        title: 'NodeJS',
        icon : 'mdi-leaf',
        value: 85,
      },
      {
        title: 'Angular Framework',
        icon : ' mdi-brightness-auto',
        value: 70,
      },
      { divider: true },
      {
        title: 'Ubuntu Server',
        icon : 'mdi-ubuntu',
        value: 70,
      },
      {
        title: 'CentOS Server',
        icon : 'mdi-linux',
        value: 60,
      },
      {
        title: 'Amazon Web Service',
        icon : 'mdi-amazon',
        value: 80,
      },
      {
        title: 'MySQL & MongoDB',
        icon : 'mdi-database',
        value: 90,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 67,
      },
      {
        title: 'C/C++',
        icon : 'mdi-language-cpp',
        value: 80,
      },
      { divider: true },
      {
        title: 'Hardware Development',
        icon : 'mdi-chip',
        value: 95,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
