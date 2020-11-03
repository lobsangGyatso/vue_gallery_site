<template>
  <div id="home">
     <Banner />
    <v-container>
        <v-row>
            <v-col v-for=" value in images" :key="value"
             cols="12"
             :md="value.size === 2 ? 6 : value.size === 3 ? 4 : undefined"
             >
              <v-card
              :height="value.prominent ? 450 : 350"
              color="grey lighten-1"
              dark
              href="#!"
              >
                <v-img
                  :src="require('@/assets/articles/snowcup.jpg')"
                  height="100%"
                  gradient="rgba(0, 0, 0, .42), rgba(0, 0, 0, .42)"
                >
                <v-row
                class="text-right"
                >
                  <v-clo>
                    <h2>Travel</h2>
                  </v-clo>
                </v-row>
                </v-img>
              </v-card>
             </v-col>
        </v-row>
    </v-container>
     <Image />
    <!-- <Article>
      <Banner />
    </Article> -->
    <About />
    <Subscribe />
    <Social />
  </div>
</template>

<script>
import About from '../components/home/About'
import Subscribe from '..//components/home/Subscribe'
import Banner from '..//components/home/Banner'
import Social from '../components/home/Social'
import Image from '../components/home/Image'
export default {
  name: 'Home',
  components: {
    About,
    Banner,
    Social,
    Image,
    Subscribe
  },
  data () {
    return {
      size: 1,
      images: [
        { hero: 'adventurealtitude.jpg', size: 2 },
        { hero: 'garden.jpg', size: 2 },
        { hero: 'pigduck.jpg', size: 1 },
        { hero: 'rain.jpg', size: 2 },
        { hero: 'spices.jpg', size: 2 },
        { hero: 'sunset.jpg', size: 3 },
        { hero: 'sunset.jpg', size: 3 },
        { hero: 'sunset.jpg', size: 3 }
      ]
    }
  }
}
</script>
