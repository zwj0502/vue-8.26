<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="uname" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="uage" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="usex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addBtn">添加</button>
      <button @click="xiugai(eid)">修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item,index) in list" :key="index">
          <td>{{id=index+1}}</td>
          <td>{{item.name}}</td>
          <td>{{item.age}}</td>
          <td>{{item.sex}}</td>
          <td>
            <button @click="delBtn(index)">删除</button>
            <button @click="bdit(item,index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>


  export default {
    data() {
      return {
        list: [{ name: 'zs', age: 18, sex: '男' }, { name: 'ls', age: 28, sex: '女' }],
        uname: '',
        uage: '',
        usex: '',
        eid: ''
      }

    },
    methods: {
      delBtn(index) {
        this.list.splice(index, 1)
      },
      addBtn() {
        if (this.uname === '' || this.uage === '') {
          return alert('请输入姓名/年龄')
        }
        const aaa = ({
          id: this.index + 1,
          name: this.uname,
          age: this.uage,
          sex: this.usex,
        })
        this.list.push(aaa)
        this.uname = ''
        this.uage = ''
        this.usex = ''
      },
      bdit(item, index) {
        this.uname = item.name
        this.uage = item.age
        this.usex = item.sex
        this.eid = index
      },
      xiugai(eid) {
        this.list[eid].name =this.uname 
        this.list[eid].age =this.uage
        this.list[eid].sex =this.usex
      }
    },
  }
</script>