<template>
    <div>
        <el-container class="content-row">
            <div class="input-tip">
                name:
            </div>
            <div class="input-field">
                <el-input v-model="queryParams.name"></el-input>
            </div>
        </el-container>
        <el-container class="content-row">
            <div class="input-tip">
                Company:
            </div>
            <div class="input-field">
                <el-input type="textarea" :rows="3" v-model="queryParams.desc"></el-input>
            </div>
        </el-container>
                <el-container class="content-row">
            <div class="input-tip">
                Phone Number:
            </div>
            <div class="input-field">
                <el-input type="textarea" :rows="3" v-model="queryParams.phone"></el-input>
            </div>
        </el-container>
                <el-container class="content-row">
            <div class="input-tip">
                Address:
            </div>
            <div class="input-field">
                <el-input type="textarea" :rows="3" v-model="queryParams.address"></el-input>
            </div>
        </el-container>
        
        <el-container class="content-row">
            <div class="input-tip">
                Photos:
            </div>
                <el-upload
                :auto-upload="false"
                :limit="1"
                list-type="picture-card">
                    <i class="el-icon-plus"></i>
                </el-upload>
        </el-container>
        <el-container class="content-row">
            <div class="input-tip">
                Document:
            </div>
            <el-upload
            :auto-upload="false"
            :limit="5"
            list-type="picture-card">
                <i class="el-icon-plus"></i>
            </el-upload>
        </el-container>
        
        <el-container class="content-row">
            <div class="input-tip">
                Associated period:
            </div>
            <div class="input-field">
                <el-date-picker
                type="daterange"
                range-separator="Tills"
                start-placeholder="Beginning"
                end-placeholder="Ending if applicable"
                v-model="queryParams.timeRange">
                </el-date-picker>
            </div>
        </el-container>
        <el-container class="content-row">
            <div class="input-tip">
                Relationship Category:
            </div>
            <div class="input-field">
                <el-select v-model="queryParams.category">
                    <el-option key="0" label="Friend" :value="0"></el-option>
                    <el-option key="1" label="Professional" :value="1"></el-option>
                    <el-option key="2" label="Pro Friend" :value="2"></el-option>
                </el-select>
            </div>
            <div style="margin-top:6px">
                <el-button type="primary" size="mini" round @click="addCategory">Add Category</el-button>
            </div>
        </el-container>
        <el-container class="content-row">
            <el-button type="success" plain @click="submit">Submit</el-button>
            <div style="margin-left:40px"></div>
            <el-button type="warning" plain @click="cancel">Cancel</el-button>
        </el-container>
    </div>
</template>

<script>
export default {
    data() {
        return {
            queryParams:{
                name:"",
                desc:"",
                phone:"",
                address:"",
                linkedIn:"",
                Interest:"",
                timeRange:"",
                category:0
            }
        }
    },
    methods: {
        cancel() {
            this.$router.go(-1)
        },
        submit() {
            this.$message({
                type:'success',
                message:'Set Basic Info：' + JSON.stringify(this.queryParams)
            })
        },
        addCategory() {
            this.$router.push({name:'Category'})
        }
    }
}
</script>