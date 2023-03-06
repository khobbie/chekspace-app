<template>
  <br />
  <br />
  <br />
  <br />

  <div style="height: 65px"></div>
  <q-card-section class="col flex items-center justify-center scroll q-mt-lg">
    <img
      class="text-left"
      style="height: 65px; width: auto"
      src="/chekspace-logo.png"
    />

    <div style="max-width: 60rem; width: 100%">
      <div class="q-pa-md">
        <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
          <q-input
            filled
            autofocus
            type="text"
            v-model="form.userId"
            label="Username"
            class="q-mb-md"
            lazy-rules
            :rules="[
              (val) =>
                (val && val.length > 0) ||
                'Please enter your username to login',
            ]"
          >
            <template #prepend>
              <q-icon name="o_person" />
            </template>
          </q-input>
          <q-input
            filled
            :type="showPasswordAs"
            v-model="form.password"
            label="Password"
            class="q-mb-lg"
            lazy-rules
            :rules="[
              (val) =>
                (val && val.length > 0) ||
                'Please enter your password to login',
            ]"
          >
            <template #prepend>
              <q-icon name="o_key" />
            </template>

            <template #append>
              <q-btn
                v-if="!form.passwordVisibility"
                flat
                round
                icon="o_visibility"
                @click="onMakeVisible"
              />
              <q-btn
                v-else
                flat
                round
                icon="o_visibility_off"
                @click="onMakeInvisible"
              />
            </template>
          </q-input>

          <div>
            <q-btn
              type="submit"
              size="17px"
              color="cyan"
              label="Login to Workspace"
              class="full-width"
              :loading="loading"
            />
          </div>
        </q-form>
      </div>
    </div>
  </q-card-section>
</template>

<script setup lang="ts">
import { QSpinnerFacebook, useQuasar } from 'quasar';
import { store } from 'quasar/wrappers';
import { useRouter } from 'vue-router';
import { computed, ref } from 'vue';

const $q = useQuasar();
const router = useRouter();
const loading = ref(false);
let timer;

const form = ref({
  userId: '',
  password: '',
  passwordVisibility: false,
});

const onSubmit = async () => {
  loading.value = true;

  setTimeout(() => {
    router.push('/workspace');
  }, 4000);
};

const onReset = () => {
  form.value = {
    userId: '',
    password: '',
    passwordVisibility: false,
  };
};

const onMakeInvisible = () => (form.value.passwordVisibility = false);
const onMakeVisible = () => (form.value.passwordVisibility = true);
const showPasswordAs = computed(() =>
  form.value.passwordVisibility ? 'text' : 'password'
);

const showLoading = () => {
  $q.loading.show({
    spinner: QSpinnerFacebook,
    spinnerColor: 'yellow',
    spinnerSize: 140,
    backgroundColor: 'purple',
    message: 'Some important process is in progress. Hang on...',
    messageColor: 'black',
  });

  // hiding in 3s
  timer = setTimeout(() => {
    $q.loading.hide();
    timer = void 0;
  }, 3000);
};
</script>
