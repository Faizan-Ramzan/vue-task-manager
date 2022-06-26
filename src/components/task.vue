<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder? 'reminder':'', 'task']">
        <h3>
            {{task.text}}
            <div class="icons">
              <i v-on:click="$emit('delete-task', task.id)" class="fas fa-times"></i>
              <i v-on:click="$emit('update-task', task)" class="fas fa-edit"></i>
            </div>
        </h3>
        <p>{{task.day}}</p>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    }
}
</script>

<style scope>
.fas.fa-times {
  color: red;
}
.fas.fa-edit {
  color: blue;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border-left: 5px solid transparent;
  position: relative;
}
.task .icons {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: 20px;
  height: 42px;
  justify-content: space-between;
  font-size: 18px;
}
.task.reminder {
  border-left-color: green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>