<template>
  <q-tab-panel name="mails">
    <div class="row q-gutter-md">
      <img
        class="text-left"
        style="height: 40px; width: auto"
        src="/chekspace-logo.png"
      />
    </div>
  </q-tab-panel>
  <q-tab-panel name="mails">
    <div class="row q-gutter-md">
      <div class="text-h6 col-12">{{ type }}</div>
      <div class="col">
        <q-input
          class="text-uppercase"
          type="search"
          borderless
          filled
          v-model.trim="searchKey"
          @keydown.enter.prevent="search"
        >
          <template v-slot:after>
            <q-btn
              color="cyan"
              label="Search"
              @click="search"
              :loading="searching"
            />
          </template>
        </q-input>
      </div>
    </div>
  </q-tab-panel>
</template>

<script setup lang="ts">
import { stringify } from 'querystring';
import { ref, watchEffect } from 'vue';

// const emits = defineEmits(['update:modelValue'])
const emit = defineEmits<{
  (e: 'update:modelValue', value: string): void;
}>();

// name: 'MySearchBox'
const props = defineProps({
  modelValue: {
    type: String,
    required: false,
  },

  type: String,

  onSearch: {
    type: Function,
    required: false,
  },
});

const searchKey = ref('');

const searching = ref(false);

// eslint-disable-next-line @typescript-eslint/ban-types
let currentDataOperator: Function;

watchEffect(() => {
  emit('update:modelValue', searchKey.value);
});

// search for records
const search = async () => {
  if (searching.value) {
    return;
  }

  if (props.onSearch) {
    // save for date reload or refresh
    currentDataOperator = props.onSearch;

    searching.value = true;
    await currentDataOperator();
    searching.value = false;
  }
};

// const menAtWork = computed(() => reloading.value || exporting || searching || filtering || resetting)
</script>
