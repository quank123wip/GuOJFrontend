<template>
    <v-container class="ma-0 pa-0">
        <vue-markdown class="line-numbers">
            <slot></slot>
        </vue-markdown>
    </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import VueMarkdown from 'vue-markdown-guoj';
import Prism from 'prismjs';
import 'prismjs/plugins/autoloader/prism-autoloader';
import 'prismjs/themes/prism-tomorrow.css';
import 'prismjs/plugins/toolbar/prism-toolbar';
import 'prismjs/plugins/toolbar/prism-toolbar.css';
import 'prismjs/plugins/line-numbers/prism-line-numbers';
import 'prismjs/plugins/line-numbers/prism-line-numbers.css';
import 'prismjs/plugins/copy-to-clipboard/prism-copy-to-clipboard';
import 'prismjs/plugins/download-button/prism-download-button';
import 'prismjs/plugins/show-language/prism-show-language';

export default Vue.extend({
    components: {
        VueMarkdown,
    },
    methods: {
        update() {
            this.$nextTick(() => {
                Prism.highlightAll();
            });
        },
    },
    mounted() {
        this.update();
    },
    updated() {
        this.update();
    },
});
</script>
<style>
code,
pre {
    border-radius: none;
    box-shadow: none !important;
}
code:after,
code:before {
    content: none !important;
}
</style>
