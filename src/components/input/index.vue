<template>
    <div class="inputs">
        <el-input v-model="inputValue" :icon="inputIcon" placeholder="请输入内容"></el-input>
    </div>
</template>

<script>
    export default {
        name: 'inputs',
        props: {
            inputIcon: {
                type: String,
                default: ''
            },
            inputRef: {
                type: String,
                default: ''
            },
            inputValue: {
                type: String,
                default: ''
            }
        },
        watch: {
            inputRef: function() {
                this.commitState()
            },
            inputValue: function() {
                this.commitState()
            }
        },
        methods: {
            commitState() {
                let data = {
                    ref: this.inputRef,
                    value: this.inputValue
                }
                this.$store.commit('setFormData', data)
            }
        }
    }
</script>

<style scoped>
    .el-input{
        width: auto;
    }

    .inputs{
        margin-bottom: 20px;
    }
</style>
