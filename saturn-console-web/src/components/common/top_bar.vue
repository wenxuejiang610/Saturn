<template>
    <div>
        <div class="top-bar">
            <span>当前域：
                <router-link tag="a" :to="{ name: 'job_overview', params: { domain: domain } }">{{this.domain}}</router-link>
            </span>
            <el-tooltip placement="right">
                <div slot="content">
                    运维负责人：<span v-for="item in person.operations" :key="item.name">{{item.name}}({{item.nick}}) </span><br/>
                    开发负责人：<span v-for="item in person.develop" :key="item.name">{{item.name}}({{item.nick}}) </span>
                </div>
                <i class="el-icon-warning"></i>
            </el-tooltip>
        </div>
        
    </div>
</template>
<script>
export default {
  props: ['domain', 'person'],
};
</script>
<style lang="sass" scoped>
.top-bar {
    padding: 0 30px;
    height: 40px;
    background: #38465a;
    font-size: 15px;
    line-height: 40px;
    color: #97a8be;
    >span {
        margin-right: 5px;
        a {
            color: #c2d0d7;
            &:hover {
                color: #fff;
            }
        }
    }
}
</style>
