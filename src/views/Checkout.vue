<template>
  <v-app>
    <v-stepper v-model="e1">
      <v-stepper-header>
        <v-stepper-step
            :complete="e1 > 1"
            step="1"
        >
         Cart
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step
            :complete="e1 > 2"
            step="2"
        >
          Payment
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step
            :complete="e1 > 3"
            step="3"
        >
          Shipping
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step
            step="4"
        >
          Confirm
        </v-stepper-step>
      </v-stepper-header>

      <v-stepper-items>
        <v-stepper-content step="1">
          <v-card
              class="mb-12"
              color="grey darken-2"
          >
            <v-card-title>
              Shopping Cart
            </v-card-title>
          </v-card>

          <v-btn
              to="/"
          >
            back
          </v-btn>
          <v-btn
              color="primary"
              @click="e1 = 2"
          >
            next
          </v-btn>
        </v-stepper-content>

        <v-stepper-content step="2">
          <v-card
              class="mb-12"
              color="grey darken-2"
          >
            <v-card-title>
              Payment Details
            </v-card-title>
          </v-card>

          <v-btn
              @click="e1 = 1"
          >
            back
          </v-btn>
          <v-btn
              color="primary"
              @click="e1 = 3"
          >
            next
          </v-btn>
        </v-stepper-content>

        <v-stepper-content step="3">
          <v-card
              class="mb-12"
              color="grey darken-2"
          >
            <v-card-title>
              Shipping Details
            </v-card-title>
          </v-card>

          <v-btn
              @click="e1 = 2"
          >
            back
          </v-btn>
          <v-btn
              color="primary"
              @click="e1 = 4"
          >
            next
          </v-btn>
        </v-stepper-content>

        <v-stepper-content step="4">
          <v-card
              class="mb-12"
              color="grey darken-2"
          >
            <v-card-title>
              Order Confirmation
            </v-card-title>
          </v-card>

          <v-btn
              @click="e1 = 3"
          >
            back
          </v-btn>

          <v-dialog
            v-model="dialog"
            width="400"
          >
            <template v-slot:activator="{ on, attrs}">
              <v-btn
                  color="primary"
                  dark
                  v-bind="attrs"
                  v-on="on"
              >
                <!--              @click=" route to different page and move > down"-->
                Order
              </v-btn>
            </template>

            <v-card>
              <v-card-title>
                Order confirmed
              </v-card-title>
              <v-card-text>
                Your order has been placed and confirmation details will be sent to your email. Thank you!
              </v-card-text>
              <v-divider></v-divider>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                    color="primary"
                    to="/"
                >
                  Return to home page
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>

        </v-stepper-content>
      </v-stepper-items>
    </v-stepper>
  </v-app>
</template>

<script>
export default {
  name: "Checkout",
  data: () => ({
    e1: 1,
    dialog: false
  })
}
</script>

<style scoped>

</style>