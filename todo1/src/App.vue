<template>
  <div id="app" style="width:300px; margin:0 auto;">
    <h1>Todo List 1</h1>
    <!-- ソートなどのメニュー -->
    <select name="task-type" id="tasl-type">
      <option value="全て表示">全て表示</option>
      <option value="未着手">未着手</option>
      <option value="進行中">進行中</option>
      <option value="完了">完了</option>
    </select>
    <select style="margin-left:20px;" name="sort" id="">
      <option value="id順">id順</option>
      <option value="名前順">名前順</option>
    </select>
    <!-- フォーム部分 -->
    <form @submit.prevent>
  <table>
    <tr>
      <th>タイトル</th>
      <th>進捗状態</th>
      <th>編集</th>
      <th>削除</th>
    </tr>
    <tr v-for="(todo,index) in todos" :key="index">
      <td>{{todo.title}}</td>
      <td>{{todo.stage}}</td>
      <td><button @click="re = !re ; addTitleToForm(index)">編集</button></td>
      <td><button @click="deletTodo(index)">削除</button></td>
    </tr>
  </table>
  <!-- 編集・追加ボタン -->
  <p>タスクを追加する</p>
  <input type="text" v-model="addTodosTitle">
  <button style="margin-left:20px;" @click="addTodos">追加</button>

<!-- うまく行っていない部分 -->
<div  v-show="re">
  <p>タスクを編集する</p>
  <input type="text" :value="changeTodos.title">
  <button style="margin-left:20px;" @click="re = !re ; editTodos">変更</button>
</div>

  </form>

  </div>
</template>

<script>
export default {
  data(){
    return {
      todos: [
        {title:"リスト作成", stage:"進行中",id:1}
      ],
      re:false,
      addTodosTitle:"",
      changeTodos:"",
    }
  },
  methods:{
    // todoの追加
    addTodos(){
      if(this.addTodosTitle){
        this.todos.push({
          title:this.addTodosTitle,
          stage:"未着手",
          id:this.todos.length+1
        },)
        this.addTodosTitle=""
      }        
    },

    // todoの削除
    deletTodo(index){
      this.todos.splice(index,1)
    },
    // 編集ボタンを押した際に、表示されたinputの枠内に選択されたTodoを出力
    addTitleToForm(index){
      let changeTodos = this.todos[index]
      this.changeTodos= changeTodos
    },

    // うまくいっていない部分。編集ができない。
    editTodos(){
      this.todos.title=this.changeTodos
    },
  }
}
</script>
