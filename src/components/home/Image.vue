<template>
    <v-container>
        <v-row>
            <v-col
             cols="12"
             :md="size === 2 ? 6 : size === 3 ? 4 : undefined"
             >
             <span>we aethe nmber one</span>
               <span>we aethe nmber one</span>
                 <span>we aethe nmber one</span>
                 <span>we aethe nmber one</span>

                 <span>we aethe nmber one</span>

             </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
  name: 'Image',

  data: () => ({
    images: [
      { src: 'adventurealtitude.jpg' },
      { src: 'garden.jpg' },
      { src: 'pigduck.jpg' },
      { src: 'rain.jpg' },
      { src: 'spices.jpg' },
      { src: 'sunset.jpg' }
    ]
  })
}
</script>
