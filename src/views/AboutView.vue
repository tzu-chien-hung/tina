<template>
  <div id="app" class="about">
    <el-form
      :model="ruleForm"
      status-icon
      :rules="rules"
      ref="ruleForm"
      label-width="100px"
      class="demo-ruleForm"
    >
      <el-form-item label="姓名" prop="name">
        <el-input v-model="ruleForm.name" autocomplete="off"></el-input>
      </el-form-item>
      <el-form-item label="年龄" prop="age">
        <el-input type="number" v-model.number="ruleForm.age"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button
          type="primary"
          @click="type == 'create' ? add() : update()"
          >{{ type == "create" ? "新增" : "更新" }}</el-button
        >
        <el-button @click="cancel">取消</el-button>
      </el-form-item>
    </el-form>
    <el-table :data="res" style="width: 100%">
      <el-table-column type="index" width="50"> </el-table-column>
      <el-table-column prop="name" label="姓名" width="180"> </el-table-column>
      <el-table-column prop="age" label="年齡"> </el-table-column>
      <el-table-column label="操作">
        <template slot-scope="scope">
          <el-button size="mini" @click="handleEdit(scope.row)">编辑</el-button>
          <el-button size="mini" type="danger" @click="handleDelete(scope.row)"
            >删除</el-button
          >
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import ElementUI from "element-ui";
import locale from "element-ui/lib/locale/lang/zh-TW";
Vue.use(ElementUI, { locale });
export default {
  name: "App",
  data() {
    return {
      res: null,
      ruleForm: { id: null, name: "", age: null },
      type: "create",
      rules: {
        name: [{ required: true, message: "請輸入姓名", trigger: "blur" }],
        age: [{ required: true, message: "請輸入年齡", trigger: "blur" }],
      },
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    add() {
      this.$refs.ruleForm.validate((valid) => {
        if (valid) {
          axios
            .post(
              "https://demo.mercuryfire.com.tw:49110/crudTest",
              this.ruleForm
            )
            .then((response) => {
              this.getData();
            })
            .catch((error) => {
              console.log(error);
            });
        } else {
          return false;
        }
      });
    },
    update() {
      axios
        .patch("https://demo.mercuryfire.com.tw:49110/crudTest", this.ruleForm)
        .then((response) => {
          this.getData();
        })
        .catch((error) => {
          console.log(error);
        });
    },
    cancel() {
      this.ruleForm = { id: null, name: "", age: null };
      this.type = "create";
      this.$refs.ruleForm.resetFields();
    },
    getData() {
      axios
        .get("https://demo.mercuryfire.com.tw:49110/crudTest/a")
        .then((response) => {
          this.res = response.data.result;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    handleEdit(content) {
      this.ruleForm = JSON.parse(JSON.stringify(content));
      this.type = "update";
    },
    handleDelete(content) {
      this.$confirm("是否確認刪除該筆資料?", "提示", {
        confirmButtonText: "確定",
        cancelButtonText: "取消",
        type: "warning",
      })
        .then(() => {
          axios
            .delete(
              "https://demo.mercuryfire.com.tw:49110/crudTest/" + content.id
            )
            .then((response) => {
              this.getData();
            })
            .catch((error) => {
              console.log(error);
            });
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
