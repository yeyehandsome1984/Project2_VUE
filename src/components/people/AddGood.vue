<template>
    <div class="content-container" direction="vertical">
        <el-tabs v-model="activeTab" type="card" @tab-click="handleClick">
            <el-tab-pane label="Basic" name="1">
                <base-info></base-info>
            </el-tab-pane>
            <el-tab-pane label="Scoring" name="2">
                <scoring-setting></scoring-setting>
            </el-tab-pane>
            <el-tab-pane label="Description" name="3">
                <description-setting></description-setting>
            </el-tab-pane>
        </el-tabs>
    </div>
</template>

<script>
import BaseInfo from './BaseInfo.vue'
import ScoringSetting from './ScoringSetting.vue'
import DescriptionSetting from './DescriptionSetting.vue'

export default {
    data() {
        return {
            activeTab:"1"
        }
    },
    components:{
        BaseInfo:BaseInfo,
        ScoringSetting:ScoringSetting,
        DescriptionSetting:DescriptionSetting
    }
}
</script>