<template>
  <div id="app" style="width:300px; margin:0 auto;">
    <h1>Todo List 1</h1>
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
  <table>
    <tr>
      <th>タイトル</th>
      <th>進捗状態</th>
      <th>編集</th>
      <th>削除</th>
    </tr>
    <tr>
      <td>リスト作成する</td>
      <td>作業中</td>
      <td><button>編集</button></td>
      <td><button>削除</button></td>
    </tr>
  </table>
  <form>
  <p>タスクを追加する</p>
  <input type="text">
  <button style="margin-left:20px;">追加</button>

  <p>タスクを編集する</p>
  <input type="text">
  <button style="margin-left:20px;">変更</button>

  </form>

  </div>
</template>




<style>

</style>
