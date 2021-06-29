<template>
  <VueEditor editor="editor" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { Editor } from '@milkdown/core';
import { VueEditor, useEditor } from '@milkdown/vue';
import { commonmark } from '@milkdown/preset-commonmark';

import '@milkdown/theme-nord/lib/theme.css';

export default defineComponent({
  name: 'Editor',
  components: {
    VueEditor,
  },
  setup: () => {
    const editor = useEditor((root) => new Editor({ root }).use(commonmark));

    return {
      editor,
    };
  }
})
</script>
