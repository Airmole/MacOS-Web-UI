<!--
 * @FilePath: /MacOS/src/view/demo/demo.vue
 * @Author: admin@hamm.cn
 * @Date: 2021-08-13 19:57:52
 * @LastEditTime: 2021-08-13 20:58:51
 * @LastEditors: admin@hamm.cn
 * Written by https://hamm.cn
 * @Description: 
-->

<template>
    <div class="demo">
        <div class="top">
            <i class="iconfont icon-apple1"></i>
            <div class="info">
                <div class="title">{{demo.title}}</div>
                <div class="desc">{{demo.desc}}</div>
            </div>
        </div>
        <div class="body">
            <el-button size="small" type="primary" @click="windowMaxSize">窗口最大化</el-button>
            <el-button size="small" type="primary" @click="windowNormalSize">普通窗口</el-button>
            <el-button size="small" type="primary" @click="windowMinSize">窗口最小化</el-button>
            <el-button size="small" type="primary" @click="windowClose">关闭当前窗口</el-button>
            <el-button size="small" type="primary" @click="windowFullSize">窗口全屏</el-button>
            <el-button size="small" type="primary" @click="openApp">打开某app</el-button>
            <el-button size="small" type="primary" @click="closeApp">关闭某app</el-button>
            <el-button size="small" type="primary" @click="setWindowTitle">修改窗口标题</el-button>
        </div>
    </div>
</template>

<style scoped>
    .demo {
        display: flex;
        flex-direction: column;
        height: 100%;
        width: 100%;
        color: #333;
        text-shadow: none;
        font-weight: 300;
    }

    .info {
        flex-grow: 1;
    }

    .top {
        display: flex;
        flex-direction: row;
        padding: 20px;
    }

    .title {
        font-size: 24px;
    }

    .iconfont {
        font-size: 48px;
        margin-right: 20px;
    }

    .desc {
        font-size: 14px;
        color: #999;
    }

    .body {
        padding: 20px;
    }

    .body button {
        display: inline-block;
        margin: 5px;
    }
</style>
<script>
    export default {
        name: "system_about",
        data() {
            return {
                demo: {
                    title: "MacOS WebUI",
                    desc: "这是一个示例APP，用于一些交互相关功能的实现"
                },
            }
        },
        created() {
        },
        methods: {
            windowMaxSize() {
                this.$emit("api", {
                    event: "windowMaxSize"
                })
            },
            windowNormalSize() {
                this.$emit("api", {
                    event: "windowNormalSize"
                })
            },
            windowMinSize() {
                this.$emit("api", {
                    event: "windowMinSize"
                })
            },
            windowFullSize() {
                this.$emit("api", {
                    event: "windowFullSize"
                })
            },
            windowClose() {
                this.$emit("api", {
                    event: "windowClose"
                })
            },
            openApp() {
                this.$emit("api", {
                    event: "openApp",
                    app: "system_about"
                })
            },
            closeApp() {
                this.$emit("api", {
                    event: "closeApp",
                    app: "system_about"
                })
            },
            setWindowTitle() {
                this.$emit("api", {
                    event: "setWindowTitle",
                    title: new Date().valueOf()
                })
            }
        }
    }
</script>