<template>
  <div
    class="transition-colors project shadow-2xl bg-white dark:bg-gray-800 rounded-lg"
  >
    <div
      class="w-full rounded-sm p-6 flex flex-col justify-between leading-normal"
    >
      <div>
        <div v-if="href" class="my-4 clearfix">
          <a class="float-right" :href="href"> 🔗 </a>
        </div>
        <div class="font-bold text-xl mb-2">{{ title }}</div>
        <p class="text-label-info text-base"><slot></slot></p>
      </div>
      <div class="py-2">
        <div class="flex items-center py-4">
          <div class="text-sm">
            <p
              v-if="hrefSource && sourceLabel"
              class="text-label-info leading-none"
            >
              <strong>{{ t('source') }}: </strong>
              <a
                class="text-blue-600 dark:hover:dark:text-gray-600 hover:text-blue-700 duration-500"
                :href="hrefSource"
                >{{ sourceLabel }}</a
              >
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
import { defineProps } from 'vue'
import { useI18n } from 'vue-i18n'
const { t } = useI18n()
defineProps({
  title: String,
  href: String,
  sourceLabel: String,
  hrefSource: String,
})
</script>
