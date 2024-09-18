<template>
  <Field
    v-slot="{ componentField, errorMessage }"
    :name
  >
    <FormItem
      :name
      :label
      :required
      :error-message="errorMessage"
      :extra
    >
      <InputText
        v-bind="componentField"
        :aria-labelledby="name"
        :invalid="!!errorMessage"
        :disabled
        :placeholder
        :size="size ?? 'small'"
      />
    </FormItem>
  </Field>
</template>

<script setup lang="ts">
import InputText from 'primevue/inputtext';
import { Field } from 'vee-validate';

import FormItem from '../ui/FormItem.vue';

type InputProps = {
  name: string;
  label: string;
  type?: string;
  required?: boolean;
  disabled?: boolean;
  placeholder?: string;
  size?: 'large' | 'small';
  extra?: string;
};

defineProps<InputProps>();
</script>

<style scoped></style>
