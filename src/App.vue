<template>
<page-header></page-header>
<font-select></font-select>
<page-article></page-article>
</template>

<script>
import Vue from 'vue'
import PageHeader from './components/PageHeader.vue'
import PageArticle from './components/PageArticle.vue'
import FontSelect from './components/FontSelect.vue'

import "./assets/less/app1.less"
const _lodash = require('lodash');


export default {
    components: {
        PageHeader,
        PageArticle,
        FontSelect
    },
}
</script>
