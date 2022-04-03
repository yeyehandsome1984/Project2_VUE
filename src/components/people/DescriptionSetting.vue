<template>
    <div style="margin-bottom:20px">
        <desc-edit @contentChange="contentChange"></desc-edit>
    </div>
    <el-container class="content-row">
        <el-button type="success" plain @click="submit" style="font-weight: bold">Submit</el-button>
        <div style="margin-left:40px"></div>
        <el-button type="warning" plain @click="cancel" style="font-weight: bold">Cancel</el-button>
    </el-container>
</template>

<script>
import DescEdit from './DescriptionEdit.vue'
export default {
    data() {
        return {
            content:""
        }
    },
    components: {
        DescEdit:DescEdit
    },
    methods: {
        contentChange(content) {
            this.content = content;
        },
        cancel() {
            this.$router.go(-1)
        },
        submit() {
            this.$message({
                type:'success',
                message:'Message Submitted：' + this.content
            })
        }
    }
}
</script>