<template>
    <div class="HelloUser">
        <p>欢迎您 , 用户xxx</p>
    </div>
    <div class="MyPage">
        <el-collapse v-model="activeNames" @change="handleChange">
            <p></p>
            <el-collapse-item title="消费信息" name="1">
                <template #title>
                    <span style="font-size:20px">消费信息</span>
                </template>
                <el-row>
                    <el-col :span="6">
                        <el-statistic title="累计订单数量" :value="55" />
                    </el-col>
                    <el-col :span="6">
                        <el-statistic :value="53">
                            <template #title>
                                <div class="title-wrapper">
                                    <span class="title-text">已完成数量</span>
                                </div>
                            </template>
                            <template #suffix>/55</template>
                        </el-statistic>
                    </el-col>
                    <el-col :span="6">
                        <el-statistic title="累计消费" :value="1720" />
                    </el-col>
                    <el-col :span="6">
                        <el-statistic title="钱包余额" :value="562">
                            <template #suffix>
                            </template>
                        </el-statistic>
                    </el-col>
                </el-row>
            </el-collapse-item>
            <p></p>
            <el-collapse-item title="个人信息" name="2">
                <template #title>
                    <span style="font-size:20px">个人信息</span>
                </template>
                <el-descriptions class="margin-top" title="个人信息表" :column="3" :size="large" border>
                    <template #extra>
                        <el-button type="primary">编辑</el-button>
                    </template>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <user />
                                </el-icon>
                                ID
                            </div>
                        </template>
                        <!-- USERINFO - ID -->
                        123
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <user />
                                </el-icon>
                                用户昵称
                            </div>
                        </template>
                        <!-- USERINFO - USERNAME -->
                        kooriookami
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <iphone />
                                </el-icon>
                                电话
                            </div>
                        </template>
                        <!-- USERINFO - telephone -->
                        18100000000
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <location />
                                </el-icon>
                                姓名
                            </div>
                        </template>
                        <!-- USERINFO - Name     -->
                        小李觉
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <tickets />
                                </el-icon>
                                等级
                            </div>
                        </template>
                        <!-- USERINFO - UserLevel   -->
                        <el-tag size="small">Level.1</el-tag>
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <office-building />
                                </el-icon>
                                身份证号
                            </div>
                        </template>
                        <!-- USERINFO - Indentify   -->
                        111111200211111111
                    </el-descriptions-item>
                    <el-descriptions-item>
                        <template #label>
                            <div class="cell-item">
                                <el-icon :style="iconStyle">
                                    <office-building />
                                </el-icon>
                                Email
                            </div>
                        </template>
                        <!-- USERINFO - Email   -->
                        tongjiUniversity@tongji.edu.cn
                    </el-descriptions-item>

                </el-descriptions>
            </el-collapse-item>
            <p></p>
            <el-collapse-item title="Efficiency" name="3">
                <div>
                    Simplify the process: keep operating process simple and intuitive;
                </div>
                <div>
                    Definite and clear: enunciate your intentions clearly so that the
                    users can quickly understand and make decisions;
                </div>
                <div>
                    Easy to identify: the interface should be straightforward, which helps
                    the users to identify and frees them from memorizing and recalling.
                </div>
            </el-collapse-item>
            <p></p>
            <el-collapse-item title="Controllability" name="4">
                <div>
                    Decision making: giving advices about operations is acceptable, but do
                    not make decisions for the users;
                </div>
                <div>
                    Controlled consequences: users should be granted the freedom to
                    operate, including canceling, aborting or terminating current
                    operation.
                </div>
            </el-collapse-item>
        </el-collapse>
    </div>
</template>
  
<script>
import {
    Iphone,
    Location,
    OfficeBuilding,
    Tickets,
    User,
} from '@element-plus/icons-vue'
import { computed, ref } from 'vue'

const size = ref('')
const iconStyle = computed(() => {
    const marginMap = {
        large: '8px',
        default: '6px',
        small: '4px',
    }
    return {
        marginRight: marginMap[size.value] || marginMap.default,
        iconStyle
    }
})

export default {
    components: {
        Iphone,
        Location,
        OfficeBuilding,
        Tickets,
        User,
    },
    setup(){
        const activeNames = ref(["1","2","3","4"])
        return{
            activeNames
        }
    }
}
</script>
  
<style>
.flex-grow {
    flex-grow: 1;
}

.el-col {
    text-align: center;
}

.HelloUser {
    margin-top: 0%; 
    font-size: 30px;
    color:black;
    /* text-shadow:0px 0px 15px #0752ff,0px 0px 15px #0752ff; */
    position: absolute;
    top: 80px;
    left: 200px;
    right: 0;
    padding: 40px;
    /* 调整组件的间距 */
    margin: 0 auto;
    max-width: 1400px;
}

.MyPage {
    border: 1px solid #ccc;
    font-size: 20px;
    position: absolute;
    top: 200px;
    left: 200px;
    right: 0;
    padding: 40px;
    /* 调整组件的间距 */
    margin: 0 auto;
    max-width: 1400px;
}

.el-descriptions {
    margin-top: 20px;
}

.cell-item {
    display: flex;
    align-items: center;
}

.margin-top {
    margin-top: 20px;
}

</style>