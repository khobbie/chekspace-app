<template>
  <q-card>
    <q-tabs
      v-model="tab"
      dense
      class="text-grey"
      active-color="primary"
      indicator-color="primary"
      align="justify"
      narrow-indicator
    >
      <q-tab name="logs" label="Verification Logs" />
      <q-tab name="graph" label="Report" />
    </q-tabs>

    <q-separator />

    <q-tab-panels v-model="tab" animated>
      <q-tab-panel name="graph">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </q-tab-panel>

      <q-tab-panel name="logs">
        <div class="text-h6"></div>

        <div style="height: auto; max-height: 550px; overflow-x: hidden">
          <div class="q-pa-md">
            <q-list>
              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >Ghana Card Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GA-474-3042</q-item-label>
                  <q-item-label caption>GPS Verification</q-item-label>
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>Naa Addo Kuffuor</q-item-label>
                  <q-item-label caption>Sanction</q-item-label>
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >ChekSpace Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >Selfie Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >ChekSpace Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >Selfie Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >ChekSpace Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >Selfie Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >ChekSpace Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >Selfie Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8</q-item-label>
                  <q-item-label caption lines="2"
                    >ChekSpace Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>

              <q-separator spaced inset />

              <q-item>
                <q-item-section>
                  <q-item-label>GHA-001943481-8-------</q-item-label>
                  <q-item-label caption lines="2"
                    >Selfie Validation</q-item-label
                  >
                </q-item-section>

                <q-item-section side top>
                  <q-item-label caption>09-DEC-2023</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </div>
        </div>
      </q-tab-panel>
    </q-tab-panels>
  </q-card>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tab = ref('logs');
</script>
