<template>
    <el-container class="container">
        <el-aside width="200px">
            <Commonaside></Commonaside>
        </el-aside>
        <el-main>Main</el-main>
    </el-container>
</template>

<script>
import Commonaside from '@/components/CommonAside'

export default {
    name: 'Main',
    components: {
      Commonaside  
    },
    data() {
        return {
            
        };
    },
    mounted() {
        
    },
    methods: {
        
    },
};
</script>

<style lang="scss" scoped>
.container{
    height: 100%;
}
</style>