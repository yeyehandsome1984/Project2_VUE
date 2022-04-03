<template>
    <div class="content-container" direction="vertical">
        <el-container class="content-row">
            <el-button type="primary" @click="addCategory">Add New Category</el-button>
        </el-container>
        <div>
        <el-table
        :data="categoryList"
        tooltip-effect="dark"
        style="width: 100%">
            <el-table-column
            label="CategoryID"
            width="100"
            prop="id">
            </el-table-column>
            <el-table-column
            label="Category"
            width="200"
            prop="name">
            </el-table-column>
            <el-table-column
            label="Person in Charge"
            width="200"
            prop="manager">
            </el-table-column>
            <el-table-column
            label="Delete"
            width="200"
            prop="time">
                <template #default="scope">
                    <el-button size="mini" @click="deleteCategory(scope.$index)">删除</el-button>
                </template>
            </el-table-column>
        </el-table>
    </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            categoryList:[
                {
                    id:1231,
                    name:"Friend",
                    manager:""
                },{
                    id:1131,
                    name:"Professional",
                    manager:""
                },{
                    id:1031,
                    name:"Friend and Pro",
                    manager:""
                }
            ]
        }
    },
    methods: {
        deleteCategory(index) {
            this.categoryList.splice(index,1)
        },
        addCategory() {
            this.$prompt('Please insert new Category',{
                confirmButtonText: 'Confirm',
                cancelButtonText: 'Cancel',
            }).then(({value})=>{
                this.categoryList.push({
                    id:1000,
                    name:value,
                    manager:"Yichen"
                })
            });
        }
    }
}
</script>