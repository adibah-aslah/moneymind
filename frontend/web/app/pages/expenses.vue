<template>
  <div class="flex flex-col gap-6">
    <!-- Header -->
    <div class="flex flex-col gap-4">
      <h1 class="text-5xl font-bold text-text-primary">💰Expenses</h1>
      <p class="text-sm font-light text-text-primary ml-8">Manage your transactions</p>
    </div>

    <!-- File Uploader -->
    <div
      class="flex justify-center items-center w-full border-2 border-dashed border-gray-300 rounded-lg p-6 bg-gray-50"
    >
      <FileUploader />
    </div>
  </div>
</template>
