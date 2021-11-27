<template>
  <section class="container">
    <h1>usersページです</h1>
    <hr>
    <router-link to="/">TOPページへ</router-link>
    <hr>
    <div class="table-zone">
        <h2 class="title">テーブルパターン1</h2>
        <table>
        <tbody>
            <tr>
            <th>ID</th>
            <th>名前</th>
            <th>メールアドレス</th>
            </tr>
            <tr>
            <td>{{ users[0].id }}</td>
            <td>{{ users[0].name }}</td>
            <td>{{ users[0].email }}</td>
            </tr>
            <tr>
            <td>{{ users[1].id }}</td>
            <td>{{ users[1].name }}</td>
            <td>{{ users[1].email }}</td>
            </tr>
            <tr>
            <td>{{ users[2].id }}</td>
            <td>{{ users[2].name }}</td>
            <td>{{ users[2].email }}</td>
            </tr>
            <tr>
            <td>{{ users[3].id }}</td>
            <td>{{ users[3].name }}</td>
            <td>{{ users[3].email }}</td>
            </tr>
            <tr>
            <td>{{ users[4].id }}</td>
            <td>{{ users[4].name }}</td>
            <td>{{ users[4].email }}</td>
            </tr>
            <tr>
            <td>{{ users[5].id }}</td>
            <td>{{ users[5].name }}</td>
            <td>{{ users[5].email }}</td>
            </tr>
            <tr>
            <td>{{ users[6].id }}</td>
            <td>{{ users[6].name }}</td>
            <td>{{ users[6].email }}</td>
            </tr>
            <tr>
            <td>{{ users[7].id }}</td>
            <td>{{ users[7].name }}</td>
            <td>{{ users[7].email }}</td>
            </tr>
            <tr>
            <td>{{ users[8].id }}</td>
            <td>{{ users[8].name }}</td>
            <td>{{ users[8].email }}</td>
            </tr>
            <tr>
            <td>{{ users[9].id }}</td>
            <td>{{ users[9].name }}</td>
            <td>{{ users[9].email }}</td>
            </tr>
        </tbody>
        </table>
        
        <h2 class="title">テーブルパターン2(for文)</h2>

        <table>
        <tbody>
            <tr>
            <th>ID</th>
            <th>name</th>
            <th>email</th>
            </tr>
            <tr v-for="user in users" :key="user.id">
            <td>{{ user.id }}</td>
            <td>{{ user.name }}</td>
            <td>{{ user.email }}</td>
            </tr>
        </tbody>
        </table>
    </div>
    <h2 class="title">リストパターン1</h2>
    <ul>
      <li>{{ users[0].id }},{{ users[0].name }},{{ users[0].email }}</li>
      <li>{{ users[1].id }},{{ users[1].name }},{{ users[1].email }}</li>
      <li>{{ users[2].id }},{{ users[2].name }},{{ users[2].email }}</li>
      <li>{{ users[3].id }},{{ users[3].name }},{{ users[3].email }}</li>
      <li>{{ users[4].id }},{{ users[4].name }},{{ users[4].email }}</li>
      <li>{{ users[5].id }},{{ users[5].name }},{{ users[5].email }}</li>
      <li>{{ users[6].id }},{{ users[6].name }},{{ users[6].email }}</li>
      <li>{{ users[7].id }},{{ users[7].name }},{{ users[7].email }}</li>
      <li>{{ users[8].id }},{{ users[8].name }},{{ users[8].email }}</li>
      <li>{{ users[9].id }},{{ users[9].name }},{{ users[9].email }}</li>
    </ul>
    <h2 class="title">リストパターン2(for文)</h2>
    <ul>
      <li v-for="user in users" :key="user.id">
      {{ user.id }},{{ user.name }},{{ user.email }}
      </li>
    </ul>
  </section>
</template>

<script>
const axios = require('axios')
let url = 'https://jsonplaceholder.typicode.com/users'

export default {
  asyncData({ params }) {
    return axios.get(url)
      .then((res) => {
        return { users: res.data }
    })
  }
}
</script>

<style>
  .table-zone {
    display: grid;
  }
  .title{
    color: navy;
  }
  table {
    border: 1px black solid ;
  }
  th {
    border: 1px black solid ;
  }
  td {
    border: 1px black solid ;
  }
  ul {
    border: 1px black solid;
  }
  li {
    list-style: none;
    border: 1px black solid;
  }
</style>