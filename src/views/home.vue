<template>
  <div>{{clickMenu(menueData[1])}}</div>
</template>
<script>
export default {
  data() {
    return {
      menueData: [
        {
          path: "/",
          name: "home",
          label: "首页",
          icon: "help",
          url: "Home/Home",
        },
        {
          path: "/login",
          name: "login",
          label: "银行",
          icon: "goods",
          url: "MallManage/MallManage",
        },
        {
          path: "/player",
          name: "player",
          label: "玩家",
          icon: "goods",
          url: "",
        },
      ],
    };
  },
  methods:{
    clickMenu(item){
        console.log(item);
        //当页面路由与跳转路由不一致时，则跳转
        if(this.$route.path !== item.path && !(this.$route.path === '/home' && item.path === '/')){
            this.$router.push(item.path)
        }
        
    }
  }
};
</script>
