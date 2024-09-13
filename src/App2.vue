<template>
    <table class="list">
          <caption>
              <h1>学生列表</h1>
          </caption>
          <thead>
              <tr>
                  <th class="col-name">姓名</th>
                  <th class="col-age">年龄</th>
                  <th class="col-sex">性别</th>
                  <th class="col-birthday">出生日期</th>
                  <th class="col-hobby">爱好</th>
                  <th class="col-addr">家庭地址</th>
                  <th class="col-remark">备注</th>
                  <th class="col-end">
                      <input type="button" class="btn-add" value="新增">
                  </th>
              </tr>
          </thead>
          <tbody></tbody>
      </table>
  
  </template>
  
  <script setup>
    import {ref} from 'vue'
    let list = ref([
        {id : 3,name:"杜子腾",age:23,sex:1,birthday:"1992-08-10",hobby:['看书', '音乐'],addr:"青岛",remark:"四大才子之一"},
        {id : 4,name:"唐伯虎",age:27,sex:0,birthday:"1945-04-10",hobby:['美食','睡觉'],addr:"济南",remark:"四大才子之一"},
        {id : 5,name:"宋江",age:27,sex:0,birthday:"1888-08-05",hobby:['游戏','睡觉'],addr:"淄博",remark:"四大才子之一"},
        {id : 6,name:"张飞",age:27,sex:1,birthday:"2002-05-10",hobby:['上网','看书'],addr:"菏泽",remark:"四大才子之一"}
    ]);
  </script>
  
  <style>
  </style>