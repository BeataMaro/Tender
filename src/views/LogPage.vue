<template>
  <v-app>
    <v-app-bar app fixed color="grey darken-4" dark class="pl-4">
      <v-toolbar-title>
        <h1 class="display-2">Tender</h1>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-dialog v-model="login" max-width="400px">
        <template v-slot:activator="{ on }">
          <v-btn text rounded class="deep-purple accent-3" v-on="on">Zaloguj</v-btn>
        </template>
        <v-card width="600">
          <v-card-title>
            <h2 class="display-1">Join us!</h2>
            <v-spacer></v-spacer>
            <v-icon small @click="login = false">mdi-close</v-icon>
          </v-card-title>
          <v-card-text>
            <v-form>
              <v-text-field label="username" prepend-icon="mdi-account-circle"></v-text-field>
              <v-text-field
                :type="showPassword ? 'text' : 'password'"
                label="password"
                prepend-icon="mdi-lock"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                @click:append="showPassword = !showPassword"
              ></v-text-field>
            </v-form>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions class="d-flex justify-space-between">
            <v-btn class="green accent-3">Register</v-btn>
            <!-- <v-spacer></v-spacer> -->
            <v-btn class="deep-purple accent-3 white--text">Log in</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>

      <!-- Search -->
      <v-dialog v-model="dialog" max-width="400px">
        <template v-slot:activator="{ on }">
          <v-btn text rounded class="ml-2 text-capitalize font-weight-light" dark v-on="on">
            <v-icon class="mr-1" small>mdi-magnify</v-icon>Szukaj
          </v-btn>
        </template>
        <v-card class="d-flex justify-center pl-10 py-2">
          <v-text-field prepend-inner-icon="mdi-magnify" label="Czego szukasz?"></v-text-field>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              dark
              medium
              class="deep-purple darken-1 text-capitalize font-weight-regular mr-5"
              @click="dialog = false"
            >Szukaj</v-btn>
          </v-card-actions>
          <v-icon small class="align-self-start mt-2 mr-2" @click="dialog = false">mdi-close</v-icon>
        </v-card>
      </v-dialog>
    </v-app-bar>
    <!-- CAROUSEL -->

    <v-carousel cycle height="500" class="mb-10" hide-delimiter-background show-arrows-on-hover>
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        transition="fade-transition"
      ></v-carousel-item>
    </v-carousel>

    <!--ARTICLES -->
    <v-container>
      <v-row>
        <v-col cols="10" md="4" class="mx-auto mt-20">
          <h1 class="text-center mb-8 headline">Nagłówek</h1>
          <p
            class="grey--text"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat reiciendis nostrum minus aliquid similique tempore omnis optio? Perferendis fugiat reprehenderit voluptatibus facilis eius dignissimos quis omnis, repellendus quasi excepturi delectus?Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque distinctio reiciendis porro excepturi quidem rerum, modi quod eius ullam unde ea culpa qui mollitia praesentium nam dignissimos, fugiat, quaerat debitis?</p>
        </v-col>

        <v-col cols="10" md="4" class="mx-auto mt-20">
          <h1 class="text-center mb-8 headline">Nagłówek</h1>
          <p
            class="grey--text"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat reiciendis nostrum minus aliquid similique tempore omnis optio? Perferendis fugiat reprehenderit voluptatibus facilis eius dignissimos quis omnis, repellendus quasi excepturi delectus?Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque distinctio reiciendis porro excepturi quidem rerum, modi quod eius ullam unde ea culpa qui mollitia praesentium nam dignissimos, fugiat, quaerat debitis?</p>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
          <v-img src="../images/Earth.jpg" alt="Planet Earth" height="400" contain class="mt-10"></v-img>
        </v-col>
      </v-row>

      <v-card class="mt-5 py-4 py-lg-5">
        <v-card-title class="justify-center mb-4 mb-md-3 text-uppercase">Główny tytuł</v-card-title>
        <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo natus veniam aut, necessitatibus possimus, non, temporibus molestias nam cupiditate atque inventore. Lorem ipsum dolor sit amet consectetur adipisicing elit. Non consequuntur corrupti provident ratione earum aut recusandae veritatis quis temporibus explicabo! Vero alias rem commodi error architecto? Ex magnam eaque Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptas consectetur delectus, nam eveniet perferendis dolor consequatur! Cumque, ducimus facilis provident deleniti autem rem, dolorem Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eos quidem, unde autem repudiandae esse explicabo ad! Nesciunt nulla perspiciatis voluptatem vitae ipsum error illo ducimus cum, officiis velit explicabo quaerat? Lorem ipsum dolor, sit amet consectetur adipisicing elit. Possimus eligendi distinctio sit nihil inventore repudiandae iure, cupiditate culpa quidem, quibusdam nisi repellat fugit, eius aspernatur minus nemo tenetur voluptatum sunt. in ad sapiente amet culpa aliquid. Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ducimus minus est consequuntur quos eveniet sunt dolorum nesciunt commodi asperiores. Eos impedit totam odit, molestias qui mollitia corporis vero et voluptates. aperiam!</v-card-text>
      </v-card>

      <v-row class="d-flex">
        <!-- first cat card -->
        <v-col cols="12" md="4">
          <v-hover v-slot:default="{ hover }">
            <v-card class="py-5" :elevation="hover ? 12 : 2">
              <v-img
                src="../images/max-baskakov-unsplash.jpg"
                alt="grey cat"
                height="300"
                contain
                class="mb-10"
              ></v-img>

              <v-card-text
                class="text-center"
              >Pierwszy ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo naum...</v-card-text>

              <v-card-actions class="d-flex justify-center">
                <v-btn fab x-small class="black white--text">
                  <v-icon x-small>mdi-chevron-double-right</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
        <!-- second cat card -->
        <v-col cols="12" sm="6" md="4">
          <v-hover v-slot="{ hover }">
            <v-card class="py-3" :elevation="hover ? 12 : 2">
              <v-img
                src="https://unsplash.it/330/400?image=40"
                alt="cats nose"
                height="300"
                contain
                class="mb-10"
              ></v-img>

              <v-card-text
                class="text-center"
              >Drugi ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo naum...</v-card-text>

              <v-card-actions>
                <v-card-text class="text-right grey--text font-italic">Read more</v-card-text>
                <!-- <v-btn fab x-small class="black white--text"> -->
                <!-- <v-icon x-small>mdi-chevron-double-right</v-icon> -->
                <!-- </v-btn> -->
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>

        <!-- Third cat card -->
        <v-col cols="12" sm="6" md="4">
          <v-hover v-slot:default="{ hover }">
            <v-card class="py-5" :elevation="hover ? 12 : 2">
              <v-img
                src="https://unsplash.it/330/400?image=40"
                alt="cats nose"
                height="300"
                contain
                class="mb-10"
              ></v-img>

              <v-card-text
                class="text-center"
              >Trzeci ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo naum...</v-card-text>

              <v-card-actions class="d-flex justify-center">
                <v-btn fab x-small class="black white--text">
                  <v-icon x-small>mdi-chevron-double-right</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
      <!-- koniec trzeciego -->
      <v-row>
        <v-col>
          <v-hover v-slot="{ hover}">
            <v-card class="py-5" :elevation="hover ? 12 : 2">
              <v-img
                src="../images/ryan-walton-dog-on-the-beach-unsplash.jpg"
                alt="cats nose"
                height="300"
                contain
                class="mb-10"
              ></v-img>

              <v-card-text
                class="text-center"
              >Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo naum...</v-card-text>

              <v-card-actions class="d-flex justify-center">
                <v-btn fab x-small class="btn deep-purple accent-4 white--text ml-3">
                  <v-icon x-small>mdi-chevron-double-right</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
        <v-col>
          <v-hover v-slot="{ hover }">
            <v-card class="py-5" :elevation="hover ? 12 : 2">
              <v-img
                src="../images/josh-hild-puppy-unsplash.jpg"
                alt="cats nose"
                height="300"
                contain
                class="mb-10"
              ></v-img>

              <v-card-text
                class="text-center"
              >Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente perspiciatis rem aspernatur incidunt eius veritatis officiis facere nemo naum...</v-card-text>

              <v-card-actions class="d-flex justify-center">
                <v-btn fab x-small class="btn deep-purple accent-4 white--text ml-3">
                  <v-icon x-small>mdi-chevron-double-right</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
      <v-row class="white--text text-center" padless>
        <v-col class="py-10">
          <v-img
            src="https://unsplash.it/330/400?image=400"
            alt="young-man-hugs-black-dog"
            height="400"
            contain
          ></v-img>
        </v-col>
        <v-col class="py-10">
          <v-img
            src="https://unsplash.it/330/400?image=109"
            alt="young-man-hugs-black-dog"
            height="400"
            contain
          ></v-img>
        </v-col>
      </v-row>
    </v-container>

    <v-card class="mx-auto grey lighten-3 py-10">
      <v-card-title
        class="deep-purple accent-3 my-6 justify-center headline white--text"
      >Do you like it?</v-card-title>
      <v-card-text>
        <v-img
          src="../images/man-hugs-big-dog-erica-magugliani.jpg"
          alt="young-man-hugs-black-dog"
          height="300"
          contain
        ></v-img>
      </v-card-text>
      <v-card-actions class="mt-5 justify-center">
        <v-rating color="amber"></v-rating>
      </v-card-actions>
    </v-card>

    <!--LOGIN MODULE--->
    <v-container>
      <v-card width="600" width-lg="900" class="mx-auto mt-5 mb-10">
        <!-- margin left i right (X-axis) i margin-top: 5px -->
        <v-card-title>
          <h2 class="display-1">Join us!</h2>
        </v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="username" prepend-icon="mdi-account-circle"></v-text-field>
            <v-text-field
              :type="showPassword ? 'text' : 'password'"
              label="password"
              prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="showPassword = !showPassword"
            ></v-text-field>
          </v-form>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn class="green accent-3">Register</v-btn>
          <v-spacer></v-spacer>
          <v-btn class="deep-purple accent-3 white--text">Log in</v-btn>
        </v-card-actions>
      </v-card>
    </v-container>
    <!-- FOOTER -->
    <v-footer padless>
      <v-row class="green">
        <v-col cols="12" class="d-flex justify-center pt-6">
          <v-btn
            class="display-flex my-3"
            v-for="link in links"
            :key="link"
            color="white"
            text
            rounded
          >
            <v-icon x-small class="mr-2">mdi-nature</v-icon>
            {{ link }}
          </v-btn>
        </v-col>
        <v-col cols="12" class="d-flex justify-center pb-6">
          <v-icon dark class="mx-5">mdi-twitter</v-icon>
          <v-icon dark class="mx-5">mdi-facebook</v-icon>
          <v-icon dark class="mx-5">mdi-instagram</v-icon>
          <v-icon dark class="mx-5">mdi-email</v-icon>
        </v-col>

        <v-col cols="12" class="text-center grey darken-4 py-6 px-10 white--text">
          <v-icon x-small dark medium class="mr-1">mdi-copyright</v-icon>
          <span
            class="caption font-weight-thin"
          >Copyright All rights reserved {{new Date().getFullYear()}}.</span>
          <v-divider></v-divider>
          <span class="caption light-green--text">
            Website designed and created by
            <strong class="caption text-capitalize">Beata Maro</strong>
            .
          </span>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      login: false,
      dialog: false,
      showPassword: false,
      links: ["Home", "About us", "Team", "Contact"],
      items: [
        {
          src: require("../images/kittitep-cat-with-colorful-eyes-unsplash.jpg")
        },
        {
          src: require("../images/Earth.jpg")
        },
        {
          src: require("../images/derek-story-lying-black-dog-purple-collar-unsplash.jpg")
        },
        {
          src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg"
        }
      ]
    };
  }
};
</script>
