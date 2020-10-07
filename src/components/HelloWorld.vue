<template>
  <v-app id="inspire">
    <v-app-bar
      app
      color="white"
      flat
    >
      <v-container class="py-0 fill-height">
        <h3>BWSU Booking Online</h3>

        <v-btn
          v-for="link in links"
          :key="link"
          text
        >
          {{ link }}
        </v-btn>

        <v-spacer></v-spacer>

        <v-responsive max-width="260">
          <v-text-field
            dense
            flat
            hide-details
            rounded
            solo-inverted
          ></v-text-field>
        </v-responsive>
      </v-container>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col>
            <v-card
              min-height="70vh"
              rounded="lg"
              class="pa-2"
            >
              <v-card-title>
                S'enregistrer à un match
              </v-card-title>
              <v-card-subtitle>Choisissez un match disponible ci-dessous :</v-card-subtitle>
              <v-row>
                <v-col cols="12" sm="4" v-for="match in matchs" :key="match.id">
                  <v-card>
                    <v-card-title>Charleroi - Zulte Waregem</v-card-title>
                    <v-card-subtitle>Inscriptions en <b>T4</b><br/>
                      Places disponibles : <b>50</b><br/>
                      Statut des inscriptions: <span style="color:red"><b>Fermé</b></span></v-card-subtitle>
                    <v-card-text>
                      <v-btn disabled>
                        S'enregistrer au match
                      </v-btn>
                      <v-btn href="/list/">
                        Voir la liste
                      </v-btn>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>



            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      links: [
        'S\'enregistrer pour un match',
        'Espace privé'
      ],
      matchs: [
        {
          id: 1,
          titre : 'Charleroi - Zulte',
          tribune: 'T4',
          places: '50',
          status: true
        },
        {
          id: 2,
          titre : 'Charleroi - Standard',
          tribune: 'T4',
          places: '50',
          status: false
        },
        {
          id: 3,
          titre : 'Charleroi - Standard',
          tribune: 'T4',
          places: '50',
          status: true
        }
      ]
    }),
  }
</script>