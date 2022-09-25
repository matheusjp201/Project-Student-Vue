<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>{{ title }}</h1>
    <input type="text" v-model="name" placeholder="Name Student"  v-on:keyup.enter="addStudent()"/>
    <button @click="addStudent">Add Student</button>

    <table border="1px">
      <thead>
        <th>Registration</th>
        <th>Name</th>
        <th>Actions</th>
      </thead>
      <tbody>
        <tr v-for="(student, index) in students" :key="index">
          <!-- <td>
            {{ student.registration }}
          </td> -->
          <td>
            {{ index+1 }}
          </td>
          <td>
            {{ student.name }}
          </td>
          <td>
            <button class="btn" @click="remove()">Remove</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      title: "Students",
      students: [
        {
          registration: 1,
          name: "josh",
        },
        {
          registration: 2,
          name: "joshua",
        },
        {
          registration: 3,
          name: "joshuas",
        }
      ]
    };
  },
  props: {},
  methods: {
    addStudent() {
      let _student = {
        name: this.name,
      }
      this.students.push(_student);
      this.name = '';
    },
    remove() {
      this.students.pop();
    },
  },
};
</script>

<style scoped>
</style>
