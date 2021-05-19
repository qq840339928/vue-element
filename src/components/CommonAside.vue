<template>
    <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
    >
        <el-menu-item v-for="item in menuNoChildren" :key="item.path">
            <i :class="item.icon"></i>
            <span slot="title">{{item.name}}</span>
        </el-menu-item>
        <el-submenu v-for="(item, index) in menuHasChildren" :key="index" :index="index + '1'">
            <template slot="title">
                <i class="el-icon-location"></i>
                <span>{{item.name}}</span>
            </template>
            <el-menu-item-group v-for="(subItem, index) in (item.children)" :key="index">
                <template slot="title">{{subItem.name}}</template>
                <el-menu-item index="1-1">孙子</el-menu-item>
                <el-menu-item index="1-2">孙女</el-menu-item>
            </el-menu-item-group>
        </el-submenu>
    </el-menu>
</template>

<script>
export default {
    name: 'Commonaside',
    computed: {
        menuHasChildren () {
            return this.menu.filter(item => item.children)
        },
        menuNoChildren () {
            return this.menu.filter(item => !item.children)
        }
    },
    data() {
        return {
            menu: [
                {
                    name: '首页',
                    path: '/',
                    icon: 'el-icon-s-home'
                },
                {
                    name: '视频管理',
                    path: '/video',
                    icon: 'el-icon-video-camera-solid'
                },
                {
                    name: '用户管理',
                    path: '/user',
                    icon: 'el-icon-user-solid'
                },
                {
                    name: '其他',
                    icon: 'el-icon-more-outline',
                    children: [
                        {
                            name: '其他他儿子',
                            path: '/otherSon',
                            icon: 'el-icon-user-solid'
                        },
                        {
                            name: '其他他闺女',
                            path: '/otherDaughter',
                            icon: 'el-icon-user-solid'
                        }
                    ]
                },
                {
                    name: '其他2',
                    icon: 'el-icon-more-outline',
                    children: [
                        {
                            name: '其他2他儿子',
                            path: '/otherSon',
                            icon: 'el-icon-user-solid'
                        },
                        {
                            name: '其他2他闺女',
                            path: '/otherDaughter',
                            icon: 'el-icon-user-solid'
                        }
                    ]
                }
            ]
        };
    },
    mounted() {
        
    },
    methods: {
        
    },
};
</script>

<style lang="scss" scoped>
.el-menu{
    height: 100%;
}
</style>