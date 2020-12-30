<template>
  <div>
    <!-- ^==== Particle Home page ==== -->
    <div class="particles-wrapper particles">
      <client-only>
        <vue-particles
          color="#ffffff"
          :particleOpacity="0.7"
          :particlesNumber="120"
          shapeType="circle"
          :particleSize="4"
          linesColor="#cccccc"
          :linesWidth="1"
          :lineLinked="true"
          :lineOpacity="0.4"
          :linesDistance="150"
          :moveSpeed="4"
          :hoverEffect="true"
          hoverMode="grab"
          :clickEffect="true"
          clickMode="push"
        >
        </vue-particles>
      </client-only>

      <!-- ^==== Home Page ==== -->
      <div
        id="home"
        class="content pa-sm-8 pa-4 d-flex align-center justify-sm-space-between justify-center flex-sm-row flex-column"
      >
        <v-card class="mt-sm-0 transparent" text rounded="0">
          <v-card-title>
            <h1 class="text-xl-h1 text-lg-h2 text-sm-h3 text-h4 title">
              <span style="font-family: 'Merienda', cursive">This is</span>
              <span style="font-family: 'Merienda', cursive">Bunrong KIT</span>
              <v-card-subtitle
                class="text-overline pa-0 text-right mr-1 mt-2 primary--text"
              >
                <span>¯\_(ツ)_/¯ aka (gary)</span>
              </v-card-subtitle>
            </h1>
          </v-card-title>
          <v-card-subtitle class="text-overline subtitle">
            <span>A full stack web developer</span>
          </v-card-subtitle>
          <v-card-text class="text-body-1 subtitle">
            Click
            <a href="https://github.com/KitBunrong">here</a>
            to view my work!
          </v-card-text>
        </v-card>
        <v-btn
          href="https://github.com/KitBunrong"
          target="_blank"
          class="kit-github mt-sm-0"
          x-small
          text
        >
          <span>connect with kit</span>
        </v-btn>
      </div>
    </div>

    <!-- ^==== Skills ==== -->
    <div id="skill" class="black pt-6">
      <v-container>
        <h3 class="text-h5 text-uppercase">Skills</h3>
      </v-container>
      <v-container>
        <v-row>
          <v-col class="col-12">
            <h4 class="text-h6 text-uppercase text-center mb-4">frontend</h4>
            <v-chip-group class="mb-4" column>
              <v-tooltip
                top
                color="black"
                v-for="(frontend, i) in frontends"
                :key="i"
              >
                <template #activator="{ on }">
                  <v-chip
                    class="gray darken-3 aos-init aos-animate"
                    :href="frontend.to"
                    :data-aos-delay="i * 100"
                    data-aos="fade-up"
                    v-on="on"
                    label
                  >
                    <v-icon :class="frontend.icons" left></v-icon>
                    {{ frontend.name }}
                  </v-chip>
                </template>
                <span>{{ frontend.tooltip }}</span>
              </v-tooltip>
            </v-chip-group>
          </v-col>

          <v-col class="col-12">
            <h4 class="text-h6 text-uppercase text-center mb-4">backend</h4>
            <v-chip-group class="mb-4" column>
              <v-tooltip
                top
                color="black"
                v-for="(backend, i) in backends"
                :key="i"
              >
                <template #activator="{ on }">
                  <v-chip
                    class="gray darken-3 aos-init aos-animate"
                    :data-aos-delay="i * 100"
                    data-aos="fade-up"
                    v-on="on"
                    :href="backend.to"
                    label
                  >
                    <v-icon :class="backend.icons" left></v-icon>
                    {{ backend.name }}
                  </v-chip>
                </template>
                <span>{{ backend.tooltip }}</span>
              </v-tooltip>
            </v-chip-group>
          </v-col>

          <v-col class="col-12">
            <h4 class="text-h6 text-uppercase text-center mb-4">tools</h4>
            <v-chip-group class="mb-4" column>
              <v-tooltip top color="black" v-for="(tool, i) in tools" :key="i">
                <template #activator="{ on }">
                  <v-chip
                    class="gray darken-3 aos-init aos-animate"
                    :data-aos-delay="i * 100"
                    data-aos="fade-up"
                    v-on="on"
                    :href="tool.to"
                    label
                  >
                    <v-icon :class="tool.icons" left></v-icon>
                    {{ tool.name }}
                  </v-chip>
                </template>
                <span>{{ tool.tooltip }}</span>
              </v-tooltip>
            </v-chip-group>
          </v-col>

          <v-col class="col-12">
            <h4 class="text-h6 text-uppercase text-center mb-4">cms</h4>
            <v-chip-group class="mb-4" column>
              <v-tooltip top color="black" v-for="(cms, i) in cmss" :key="i">
                <template #activator="{ on }">
                  <v-chip
                    class="gray darken-3 aos-init aos-animate"
                    :data-aos-delay="i * 100"
                    data-aos="fade-up"
                    v-on="on"
                    :href="cms.to"
                    label
                  >
                    <v-icon :class="cms.icons" left></v-icon>
                    {{ cms.name }}
                  </v-chip>
                </template>
                <span>{{ cms.tooltip }}</span>
              </v-tooltip>
            </v-chip-group>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      frontends: [
        {
          to: 'https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5',
          icons: 'mdi mdi-language-html5',
          name: 'HTML',
          tooltip: 'The bare bone of Webpage',
        },
        {
          to: 'https://developer.mozilla.org/en-US/docs/Web/CSS',
          icons: 'mdi mdi-language-css3',
          name: 'CSS3',
          tooltip: 'The skin of the Webpage',
        },
        {
          to: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript',
          icons: 'mdi mdi-language-javascript',
          name: 'JavaScript',
          tooltip: 'The hearth of Javascript',
        },
        {
          to: 'https://vuejs.org/',
          icons: 'mdi mdi-vuejs',
          name: 'VueJS',
          tooltip: 'Progressive Javascript Framework',
        },
        {
          to: 'https://en.wikipedia.org/wiki/Representational_state_transfer',
          icons: '',
          name: 'REST API',
          tooltip: 'Application Programming language(API)',
        },
        {
          to: 'https://sass-lang.com/',
          icons: 'mdi mdi-sass',
          name: 'Sass',
          tooltip: 'Stylesheet language compiled to CSS',
        },
        {
          to: 'https://nuxtjs.org/',
          icons: 'mdi mdi-nuxt',
          name: 'NuxtJS',
          tooltip: 'Framework using Vue',
        },
        {
          to: 'https://en.wikipedia.org/wiki/Responsive_web_design',
          icons: 'mdi mdi-responsive',
          name: 'Responsive',
          tooltip: 'Design Web layouts for differnt screen size',
        },
        {
          to: 'https://getbootstrap.com/',
          icons: 'mdi mdi-bootstrap',
          name: 'BootStrap',
          tooltip: 'CSS Framework',
        },
        {
          to: 'https://tailwindcss.com/',
          icons: 'mdi mdi-tailwind',
          name: 'TailwindCSS',
          tooltip: 'CSS Framework',
        },
      ],
      backends: [
        {
          to: 'https://www.mysql.com/',
          icons: 'mdi mdi-database-search',
          name: 'MYSQL',
          tooltip: 'Open-source database management system',
        },
        {
          to: 'https://www.php.net/',
          icons: 'mdi mdi-language-php',
          name: 'PHP',
          tooltip: 'Side-server scripting language',
        },
        {
          to: 'https://redis.io/',
          icons: '',
          name: 'Redis',
          tooltip: 'In-memory data structure',
        },
        {
          to: 'https://www.rabbitmq.com/',
          icons: '',
          name: 'RabbitMQ',
          tooltip: 'Message-broker',
        },
      ],
      tools: [
        {
          to: 'https://git-scm.com/',
          icons: 'mdi mdi-git',
          name: 'Git',
          tooltip: 'Source-version control system',
        },
        {
          to: 'https://www.docker.com/',
          icons: 'mdi mdi-docker',
          name: 'Docker',
          tooltip: 'Containerized applications',
        },
        {
          to: 'https://www.nginx.com/',
          icons: '',
          name: 'Nginx',
          tooltip: 'Web Server',
        },
        {
          to: 'https://www.apache.org/',
          icons: '',
          name: 'Apache',
          tooltip: 'Web Server',
        },
        {
          to: 'https://www.npmjs.com/',
          icons: 'mdi mdi-npm',
          name: 'NPM',
          tooltip: 'Node package manager',
        },
        {
          to: 'https://yarnpkg.com/',
          icons: '',
          name: 'Yarn',
          tooltip: 'Node package manager',
        },
      ],
      cmss: [
        {
          to: 'https://wordpress.org/',
          icons: 'mdi mdi-wordpress',
          name: 'WordPress',
          tooltip: 'Popular open-source CMS',
        },
        {
          to: 'https://ghost.org/',
          icons: '',
          name: 'Ghost',
          tooltip: 'Open-source CMS using Node.js',
        },
        {
          to: 'https://directus.io/',
          icons: '',
          name: 'Directus',
          tooltip: 'Open-source headless CMS',
        },
        {
          to: 'https://getcockpit.com/',
          icons: '',
          name: 'Cockpit',
          tooltip: 'Open-source headless CMS',
        },
      ],
    }
  },
  components: {},
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Merienda:wght@700&family=Patrick+Hand&display=swap');

.particles {
  width: 100%;
  height: 100vh;
  background: linear-gradient(180deg, #000, #000 44%, transparent);
  margin-bottom: 40px;
}

#particles-js {
  height: 100%;
}

.particles-wrapper {
  position: relative;
}

.content {
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
}

.particles-wrapper .content a {
  pointer-events: auto;
}

.kit-github {
  align-self: flex-end;
}

.v-slide-group__content {
  justify-content: center;
}
</style>
