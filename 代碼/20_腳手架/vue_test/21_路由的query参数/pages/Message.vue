<template>
  <div>
    <ul>
      <li v-for="m in messageList" :key="m.id">
        <!-- 跳轉路由並攜帶query參數,to的字符串寫法 -->
        <!-- <router-link
          :to="'/home/message/detail?id=' + m.id + '&title=' + m.title + '!'"
          >{{ m.title }}</router-link
        >&nbsp;&nbsp; -->
        <!-- <router-link :to="`/home/message/detail?id=${m.id}&title=${m.title}`">{{
          m.title
        }}</router-link
        >&nbsp;&nbsp; -->
        
        <!-- 跳轉路由並攜帶query參數,to的對象寫法 -->
        <router-link
          :to="{
            path: '/home/message/detail',
            query: {
              id: m.id,
              title: m.title,
            },
          }"
          >{{ m.title }}</router-link
        >&nbsp;&nbsp;
      </li>
    </ul>
    <hr />
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "Message",
  data() {
    return {
      messageList: [
        { id: "001", title: "消息001" },
        { id: "002", title: "消息002" },
        { id: "003", title: "消息003" },
      ],
    };
  },
};
</script>

<style>
</style>