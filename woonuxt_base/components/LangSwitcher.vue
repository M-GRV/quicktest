<script setup>
const { locales, locale, setLocaleCookie } = useI18n();

watch(locale, (newLocale) => {
  setLocaleCookie(newLocale);
});
</script>

<template>
  <select v-model="locale" aria-label="Language switcher">
    <option v-for="locale in locales" :key="locale" :value="locale.code">
      {{ locale.name }}
    </option>
  </select>
</template>
