<!-- eslint-disable no-undef -->
<template>

  <div class="todo-form">
    <div class="todo-group">
      <h1>Danh sách nhân viên</h1>
      <button class="btn Add-Edit-todo" @click="isSubmit = !isSubmit">
        AddTodo
      </button>
      <div class="todo-table">
        <table class="table">
          <thead>
            <th>STT</th>
            <th>Name</th>
            <th>Age</th>
            <th>Adress</th>
            <th>Position</th>
            <th>Add/Remove</th>
          </thead>
          <tbody v-for="(item, index) in items" :key="index">
            <th>{{ index + 1 }}</th>
            <th>{{ item.name }}</th>
            <th>{{ item.age }}</th>
            <th>{{ item.adress }}</th>
            <th>{{ item.position }}</th>
            <th>
<<<<<<< HEAD
              <i class="fa-solid fa-pen-to-square" @click="showEditFC(item, index)"></i>
=======
              <i
                class="fa-solid fa-pen-to-square"
                @click="showEditFC(item, index)"
              ></i>
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
              <span>or</span>
              <i class="fa-solid fa-trash-can" @click="deleteTodo(index)"></i>
            </th>
          </tbody>
        </table>
      </div>
      <div v-for="(value, index) in todoList" :key="index">
        {{ value.title }}
      </div>
    </div>
  </div>
  <!-- form modal add todolist -->
  <div class="form-modal" v-if="isSubmit">
    <div class="modal-warp">
      <div class="modal-group">
        <p>Name:</p>
        <input type="text" v-model="newItem.name" />
      </div>
      <div class="modal-group">
        <p>Age:</p>
        <input type="text" v-model="newItem.age" />
      </div>
      <div class="modal-group">
        <p>adress:</p>
        <input type="text" v-model="newItem.adress" />
      </div>
      <div class="modal-group">
        <p>Position:</p>
        <input type="text" v-model="newItem.position" />
      </div>
      <div class="warp-note">
        <button class="btn submit" @click="isSubmit = !isSubmit">Cancle</button>
        <button class="btn submit" @click="addItems">Add</button>
      </div>
    </div>
  </div>
  <!-- form edit modal todolist -->
<<<<<<< HEAD
   <div class="form-modal2" v-if="showEditModal">
    <div class="modal-warp">
      <div class="modal-group">
        <p>Name:</p>
        <input type="text" v-model="formEdit.name">
=======
  <div class="form-modal2" v-if="showEditModal">
    <div class="modal-warp">
      <div class="modal-group">
        <p>Name:</p>
        <input type="text" v-model="formEdit.name" />
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
      </div>
      <div class="modal-group">
        <p>Age:</p>
<<<<<<< HEAD
        <input type="text" v-model="formEdit.age">
=======
        <input type="text" v-model="formEdit.age" />
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
      </div>
      <div class="modal-group">
        <p>adress:</p>
<<<<<<< HEAD
        <input type="text" v-model="formEdit.adress">
=======
        <input type="text" v-model="formEdit.adress" />
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
      </div>
      <div class="modal-group">
        <p>Position:</p>
<<<<<<< HEAD
        <input type="text" v-model="formEdit.position">
      </div >
      <div class="warp-note">
        <button class="btn submit" @click="showEditModal = !showEditModal">Cancle</button>
=======
        <input type="text" v-model="formEdit.position" />
      </div>
      <div class="warp-note">
        <button class="btn submit" @click="showEditModal = !showEditModal">
          Cancle
        </button>
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
        <button class="btn submit" @click="edit">Edit</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: "Nguyễn Văn Linh",
          age: 27,
          adress: "Quảng Nam",
          position: "Nhân viên",
          done: false,
        },
        {
          name: "Phan thị Dung",
          age: 26,
          adress: "Quảng Nam",
          position: "QC",
          done: false,
        },
        {
          name: "Nguyễn Lê Đình tiên",
          age: 27,
          adress: "Quảng Nam",
          position: "Nhân viên",
          done: false,
        },
        {
          name: "Nguyễn Văn B",
          age: 27,
          adress: "Quảng Nam",
          position: "Nhân viên",
          done: false,
        },
      ],
<<<<<<< HEAD
      newItem:{name:'',age:'',adress:'',position:'',done:false,},
      isSubmit:false,
      showEditModal:false,
      formEdit:{name:'',age:'',adress:'',position:'',done:false,},
      editIndex:'',
      hello:[],
    }
  },
  
  methods:{
    addItems(){
     if(this.newItem.name==="" || this.newItem.age==="" || this.newItem.adress==="" || this.newItem.position===""){
      alert("Vui lòng nhập đầy đủ dữ liệu")
     }else{
      this.items.push(...this.newItem)
      this.newItem={name:'',age:'',adress:'',position:'',done:false,}
      this.isSubmit=false
     }
    },
    deleteTodo(index){
      if(confirm('Bạn có muốn xoá không?')){
        this.items.splice(index,1)
      }  
    },
    showEditFC(item, index) {
      this.showEditModal = !this.showEditModal;
      this.formEdit = item;
      this.editIndex = index;
    },
    edit(){
      if(confirm('Bạn có muốn thay đổi không?')){
        this.items[this.editIndex]=this.formEdit
        this.showEditModal = !this.showEditModal;
      }
      
    }
   
  }
}
=======
      newItem: { name: "", age: "", adress: "", position: "", done: false },
      isSubmit: false,
      showEditModal: false,
      editIndex: "",
      todoList: [],
      formEdit: {
        name: "",
        age: "",
        adress: "",
        position: "",
        done: false,
      },
    };
  },
  methods: {
    addItems() {
      if (
        this.newItem.name === "" ||
        this.newItem.age === "" ||
        this.newItem.adress === "" ||
        this.newItem.position === ""
      ) {
        alert("Vui lòng nhập đầy đủ dữ liệu");
      } else {
        this.items.push({ ...this.newItem });
        this.newItem = {
          name: "",
          age: "",
          adress: "",
          position: "",
          done: false,
        };
        this.isSubmit = false;
      }
    },
    showEditFC(item, index) {
      this.showEditModal = !this.showEditModal;
      this.formEdit = {...item};
      this.editIndex = index;
    },
    edit() {
      this.items[this.editIndex] = this.formEdit;
      this.showEditModal = !this.showEditModal
    },
    deleteTodo(index) {
      this.items.splice(index, 1);
    },
    async getTodo() {},
  },
};
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
</script>

<style lang="scss">
.todo-form {
  width: 100%;
  min-height: 100vh;
  position: relative;
  padding-bottom: 120px;
  .todo-group {
    h1 {
      text-align: center;
      padding: 100px;
      color: gold;
    }
    .Add-Edit-todo {
      display: flex;
      margin: 8px auto;
      background-color: navy;
      color: #fff;
    }
    .todo-table {
      padding-bottom: 30px;
      .table {
        margin: auto;
        width: 95%;
        text-align: center;
<<<<<<< HEAD
        padding: 50px;
        color:gold;
      }
      .Add-Edit-todo{
        display:flex;
        margin: 8px auto;
        background-color:navy;
        color:#fff;
      }
      .todo-table {
        padding-bottom:30px;
        .table{
          margin:auto;
          width: 95%;
          text-align:center;
          thead{
            th{
              border:2px solid rgb(101, 10, 10);
            }
=======
        thead {
          th {
            border: 2px solid rgb(101, 10, 10);
>>>>>>> cc6e9386e4fec0ae22091378769a3405d2103ac9
          }
        }
        tbody {
          th {
            border: 2px solid rgb(101, 10, 10);
            i:nth-child(1) {
              background-color: rgb(175, 77, 25);
              padding: 4px 8px;
              border-radius: 4px;
            }
            span {
              margin: 4px;
              color: rgb(104, 24, 24);
            }
            i:nth-child(3) {
              background-color: rgb(221, 141, 21);
              padding: 4px 8px;
              border-radius: 4px;
            }
          }
        }
      }
    }
  }
}
.form-modal,
.form-modal2 {
  height: 100%;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.3);
  .modal-warp {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 50%;
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: rgb(85, 91, 255) 0px 0px 0px 3px,
      rgb(31, 193, 27) 0px 0px 0px 6px, rgb(255, 217, 19) 0px 0px 0px 9px,
      rgb(255, 156, 85) 0px 0px 0px 12px, rgb(255, 85, 85) 0px 0px 0px 15px;
    .modal-group {
      display: flex;
      margin: 12px auto 12px auto;

      p {
        width: 100px;
        margin: 0;
        line-height: 42px;
      }
      input {
        padding: 8px;
        width: 400px;
        outline: none;
        border-radius: 8px;
        border: 1px solid #ccc;
      }
    }
    .warp-note {
      padding: 8px;
      align-self: flex-end;
      .submit {
        width: 80px;
        margin: 8px;
        color: #fff;
        background-color: navy;
      }
    }
  }
}
</style>
