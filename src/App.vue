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
        <tbody @click="removeHandler">
          <tr v-for="item in list" v-bind:key="item.id">
            <td>{{item.name}}</td>
            <td>{{item.age}}</td>
            <td>{{item.sex ===1?'男':'女'}}</td>
            <td>{{ item.birthday }}</td>
            <td>
              <span v-for="item in item.hobby" v-bind:key="item">{{ item }}</span>
            </td>
            <td>{{item.addr}}</td>
            <td>{{item.remark}}</td>
            <td>
                <input type="button" value="删除" :data-id="item.id" class='btn-remove'>
                <input type="button" value="修改" :data-id="item.id" class='btn-update'>
            </td> 
          </tr>
        </tbody>
    </table>

    <div class="dialog" v-show="isEdit">
        <form action="" class="edit" name="edit">
            <input type="hidden" name="id" value="0">
            <label class="form-item">
                <span>姓名：</span>
                <input type="text" name="name" placeholder="请输入姓名..." v-model="name" required autofocus>
            </label>
            <label class="form-item">
                <span>年龄：</span>
                <input type="text" name="age" placeholder="请输入年龄..." required>
            </label>
            <label class="form-item">
                <span>性别：</span>
                <input type="radio" name="sex" value="1" checked>男
                <input type="radio" name="sex" value="0">女
            </label>
            <label class="form-item">
                <span>出生日期：</span>
                <input type="date" name="birthday">
            </label>
            <label class="form-item">
                <span>爱好：</span>
                <input type="checkbox" name="hobby" value="看书">看书
                <input type="checkbox" name="hobby" value="音乐">音乐
                <input type="checkbox" name="hobby" value="美食">美食
                <input type="checkbox" name="hobby" value="上网">上网
                <input type="checkbox" name="hobby" value="睡觉">睡觉
                <input type="checkbox" name="hobby" value="游戏">游戏
            </label>
            
            <label class="form-item">
                <span>地址：</span>
                <select name="addr">
                    <option value="青岛">青岛</option>
                    <option value="济南">济南</option>
                    <option value="淄博">淄博</option>
                    <option value="菏泽">菏泽</option>
                </select>
            </label>
            <label class="form-item">
                <span>备注：</span>
                <textarea name="remark" cols="20" rows="3" placeholder="请输入.."></textarea>
            </label>
            <label class="form-item">
                <input type="submit" value="确定" class="btn-save">
                <input type="button" value="取消" class="btn-cancel">
            </label>
        </form>
    </div>
</template>

<script setup>
  import {ref} from 'vue'
  const isEdit = ref(true);
  const name = ref("");
  const age = ref(0);
  const sex = ref()

  const list = ref([
      {id : 3,name:"杜子腾",age:23,sex:1,birthday:"1992-08-10",hobby:['看书', '音乐'],addr:"青岛",remark:"四大才子之一"},
      {id : 4,name:"唐伯虎",age:27,sex:0,birthday:"1945-04-10",hobby:['美食','睡觉'],addr:"济南",remark:"四大才子之一"},
      {id : 5,name:"宋江",age:27,sex:0,birthday:"1888-08-05",hobby:['游戏','睡觉'],addr:"淄博",remark:"四大才子之一"},
      {id : 6,name:"张飞",age:27,sex:1,birthday:"2002-05-10",hobby:['上网','看书'],addr:"菏泽",remark:"四大才子之一"}
  ]);
  const removeHandler = e=>{
    if(!e.target.classList.contains("btn-remove")) {return;} 
    if(!confirm('真删？')){return;}
    var removeId = parseInt(e.target.dataset.id);
    const i=list.value.findIndex(item=>item.id===removeId);
    list.value.splice(i,1);
    alert('删除成功..');
};









</script>

<style>
  .list, .list th, .list td {
    border: 1px solid #0094ff;
    border-collapse: collapse;
  }
  .list th, .list td {
    padding: 20px 30px;
    text-align: left;
  }
  .col-name {min-width:80px;}
  .col-age, .col-sex {min-width:50px;}
  .col-birthday {min-width:130px;}
  .col-hobby {min-width:200px;}
  .col-addr {min-width:100px;}
  .col-remark {min-width:200px;}
  .col-end {min-width:150px;}

  .dialog {
    position: fixed;
    left: 0;top: 0;
    width: 100%;height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex; 
    justify-content: center; 
    align-items: center; 
  }

  .edit {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    width: 500px;
    padding: 20px;
    border-radius: 8px;
  }
</style>