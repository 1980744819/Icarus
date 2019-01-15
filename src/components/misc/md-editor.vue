<template>
<el-row>
    <el-col :span="24">
        <el-row>
            <el-col :span="24">
            </el-col>
        </el-row>
        <el-row >
            <el-col :span="12">
                <el-card>
                    <el-input type="textarea" placeholder="please input" :rows="18" v-model="source"></el-input>
                </el-card>
            </el-col>
            <el-col :span="12">               
                <el-card>
                        <vue-markdown :watches="['show','html','breaks','linkify','emoji','typographer','toc']"
                        :source="source" :show="show" :html="html" :breaks="breaks" :linkify="linkify"
                        :emoji="emoji" :typographer="typographer" :toc="toc" v-on:rendered="allRight"
                        v-on:toc-rendered="tocAllRight" toc-id="toc"></vue-markdown>
                </el-card>
            </el-col>
        </el-row>
    </el-col>
</el-row>

</template>
<script>
import VueMarkdown from 'vue-markdown'
import 'katex/dist/katex.min.css'
export default {
    name: 'md-editor',
    data () {
        return {
            source: '## a',
            show: true,
            html: false,
            breaks: true,
            linkify: false,
            emoji: true,
            typographer: true,
            toc: false
        }
    },
    components: {
        VueMarkdown
    }
}
</script>

<style>
.el-card {
height: 400px;
}

</style>
