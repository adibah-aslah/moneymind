<script setup lang="ts">
import { ref } from 'vue';
import { Icon } from '@iconify/vue';

const file = ref<File | null>(null);

function handleFileUpload(e: Event) {
  const target = e.target as HTMLInputElement;
  if (target.files?.length) {
    file.value = target.files[0];
    console.log('selected:', file.value.name);
  }
}
</script>

<template>
  <div class="w-full text-center">
    <div class="flex flex-col items-center justify-center gap-2">
      <div class="flex flex-row justify-center items-center">
        <label><Icon icon="material-symbols:folder-outline" class="text-6xl" /></label>
        <div class="flex flex-col items-start justify-center gap-1 p-4">
          <label class="text-text-primary text-sm">Drop your CSV file here</label>
          <label class="cursor-pointer text-sm transition-colors text-secondary-600">
            or [browse here]
            <input type="file" accept=".csv,.pdf" @change="handleFileUpload" class="hidden" />
          </label>
          <label class="text-xs text-neutral-500 font-light"
            >Supports CSV files up to 5MB (maximum 25 expenses)</label
          >
          <p v-if="file" class="text-sm text-gray-500">Selected: {{ file?.name }}</p>
        </div>
      </div>
      <label
        class="cursor-pointer text-sm bg-primary text-white p-2 rounded-lg flex gap-2 justify-center items-center w-fit"
        ><Icon icon="material-symbols:upload" class="text-xl" />
        <p>Upload CSV</p></label
      >
      <label
        class="cursor-pointer text-sm border border-primary text-text-primary p-2 rounded-lg flex gap-2 justify-center items-center w-fit"
        ><Icon icon="simple-line-icons:plus" class="text-xl" />
        <p>Add Expenses with JSON Format</p></label
      >
    </div>
  </div>
</template>
