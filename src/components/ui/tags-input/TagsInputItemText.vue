<script setup lang="ts">
import { cn } from '@/lib/utils';
import { TagsInputItemText, type TagsInputItemTextProps, useForwardProps } from 'radix-vue';
import { type HTMLAttributes, computed } from 'vue';

const props = defineProps<TagsInputItemTextProps & { class?: HTMLAttributes['class'] }>();

const delegatedProps = computed(() => {
  const { class: _, ...delegated } = props;

  return delegated;
});

const forwardedProps = useForwardProps(delegatedProps);
</script>

<template>
  <TagsInputItemText v-bind="forwardedProps" :class="cn('rounded bg-transparent px-2 py-1 text-sm', props.class)">
    <slot />
  </TagsInputItemText>
</template>
