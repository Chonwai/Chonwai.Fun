<template>
    <div class="container">
        <p>Fuck!</p>
        <p class="font-bold">Fuck!</p>
        <el-button type="text" @click="dialogVisible = true">Click !</el-button>

        <el-dialog
            title="Message"
            :visible.sync="dialogVisible"
            width="30%"
            :before-close="handleClose"
        >
            <span>Hi</span>
            <span slot="footer" class="dialog-footer">
                <el-button @click="dialogVisible = false">取消</el-button>
                <el-button type="primary" @click="dialogVisible = false">確定</el-button>
            </span>
        </el-dialog>
    </div>
</template>

<script>
export default {
    data() {
        return {
            dialogVisible: false,
        };
    },
    methods: {
        handleClose(done) {
            this.$confirm('確定關閉？')
                .then(_ => {
                    done();
                })
                .catch(_ => {});
        },
    },
};
</script>
