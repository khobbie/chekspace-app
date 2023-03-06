<template>
  <div class="bg-grey-1 fullscreen">
    <q-tab-panel name="mails">
      <img
        class="text-left"
        style="height: 40px; width: auto"
        src="/chekspace-logo.png"
      />
    </q-tab-panel>
    <q-tab-panels v-model="tab" animated class="bg-grey-1">
      <q-tab-panel name="mails">
        <div class="row q-gutter-md">
          <div class="row">
            <div class="text-h6 col-12 q-mb-lg">Verification Workspace</div>
            <br />
            <br />

            <q-card
              flat
              bordered
              class="my-card col-6"
              @click="onSeletOperation('Card Validation')"
            >
              <q-card-section class="text-center">
                <div class="text-h6">
                  <q-icon size="60px" color="blue-cyan" name="o_badge" />
                </div>
                <div class="text-h6">Card</div>
              </q-card-section>
            </q-card>

            <q-card
              flat
              bordered
              class="my-card col-6"
              @click="onSeletOperation('Selfie Verification')"
            >
              <q-card-section class="text-center">
                <div class="text-h6">
                  <q-icon size="60px" color="blue-cyan" name="o_camera_front" />
                </div>
                <div class="text-h6">Selfie</div>
              </q-card-section>
            </q-card>

            <q-card
              flat
              bordered
              class="my-card col-6"
              @click="onSeletOperation('Quick Verification')"
            >
              <q-card-section class="text-center">
                <div class="text-h6">
                  <q-icon size="60px" color="blue-cyan" name="o_credit_score" />
                </div>
                <div class="text-h6">Quick</div>
              </q-card-section>
            </q-card>

            <q-card
              flat
              bordered
              class="my-card col-6"
              @click="onSeletOperation('GPS Verification')"
            >
              <q-card-section class="text-center">
                <div class="text-h6">
                  <q-icon
                    size="60px"
                    color="blue-cyan"
                    name="o_share_location"
                  />
                </div>
                <div class="text-h6">GPS</div>
              </q-card-section>
            </q-card>

            <q-card
              flat
              bordered
              class="my-card col-6"
              @click="onSeletOperation('Sanction Screening')"
            >
              <q-card-section class="text-center">
                <div class="text-h6">
                  <q-icon
                    size="60px"
                    color="blue-cyan"
                    name="o_admin_panel_settings"
                  />
                </div>
                <div class="text-h6">Sanction</div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </q-tab-panel>

      <q-tab-panel name="alarms">
        <VerificationLog />
      </q-tab-panel>

      <q-tab-panel name="movies">
        <div class="text-h6">My Profile</div>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </q-tab-panel>
    </q-tab-panels>

    <q-footer class="bg-white full-width">
      <q-tabs v-model="tab" dense align="justify">
        <q-tab class="text-cyan" name="mails" icon="dashboard" label="Space" />
        <q-tab
          class="text-cyan"
          name="alarms"
          icon="o_bar_chart"
          label="Report"
        />
        <q-tab
          class="text-cyan"
          name="movies"
          icon="o_person_2"
          label="Profile"
        />
        <q-tab
          class="text-cyan"
          name="movies"
          icon="lock"
          label="Logout"
          @click="confirm = true"
        />
      </q-tabs>
    </q-footer>

    <my-full-dialog v-model="verificationDialog">
      <MySearchBar :type="workspaceType" />
      <!-- <CameraComponent v-if="workspaceType == 'selfie'" /> -->
    </my-full-dialog>
  </div>

  <q-dialog v-model="confirm" persistent>
    <q-card>
      <q-card-section class="row items-center">
        <q-avatar icon="lock" color="primary" text-color="white" />
        <br />
        <span class="q-ml-sm">Are you sure, you want to logout?</span>
      </q-card-section>

      <q-card-actions align="right">
        <q-btn flat label="Cancel" color="primary" v-close-popup />
        <q-btn flat label="Logout" color="primary" @click="logout()" />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import MyFullDialog from 'src/components/MyFullDialog.vue';
import VerificationLog from 'src/components/report/VerificationLogComponent.vue';
import CameraComponent from 'src/components/workspace/selfie/CameraComponent.vue';
import { useRouter } from 'vue-router';
import MySearchBar from 'src/components/MySearchBar.vue';

const router = useRouter();

const verificationDialog = ref(false);
const tab = ref('mails');
const confirm = ref(false);
const workspaceType = ref('Card Validation');

const onSeletOperation = async (type: string) => {
  verificationDialog.value = !verificationDialog.value;
  workspaceType.value = type;
};

const logout = async () => {
  confirm.value = !confirm.value;
  router.push('/');
};
</script>
