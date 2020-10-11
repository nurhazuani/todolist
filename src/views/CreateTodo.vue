<template>
    <div  class="row">
 
      <div class="col-12 py-5">
        <!-- <h2>{{message}}</h2> -->

         <form @submit.prevent="addTodo()">
            <b-input-group>
                    <input
                        v-model="newTodo"
                        type="text"
                        class="form-control"
                        placeholder="Add new task..."
            />
             
           <b-button variant="outline-secondary" type="submit">Add Task</b-button>
          </b-input-group>
          </form>
      </div>
          
    </div>
</template>

<script>
export default {
     data() {
        return {
        // message: "TO-DO LISt",
        newTodo: ""
        };
    },
    methods: {
        addTodo() {
        if (this.newTodo.length > 0) {
            this.$emit("on-new-todo", this.newTodo);
        }
        this.newTodo = "";
        }
  }
     
}
</script>

<style scoped>


</style>