<template>
    <div>
        <div class="title_top">
           <el-popover
              ref="popover3"
              placement="bottom-start"
              width="900"
              :disabled="updateShow"
              trigger="click">
               <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="80px" size="small" class="demo-ruleForm">
                  <div style="float:left;width:350px;margin-left:100px;margin-top:30px">
                      <el-form-item label="姓名" prop="name">
                        <el-input v-model="ruleForm.name" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="电话" prop="phone">
                        <el-input v-model="ruleForm.phone" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="纹眉" prop="wenmei">
                        <el-input v-model="ruleForm.wenmei" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="美睫" prop="meijie">
                        <el-input v-model="ruleForm.meijie" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="美甲" prop="meijia">
                        <el-input v-model="ruleForm.meijia" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="脱毛" prop="tuomao">
                        <el-input v-model="ruleForm.tuomao" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="祛斑" prop="quban">
                        <el-input v-model="ruleForm.quban" class="add_input"></el-input>
                      </el-form-item>
                  </div>
                  <div style="float:left;width:350px;margin-top:30px">
                      <el-form-item label="水光" prop="shuiguang">
                        <el-input v-model="ruleForm.shuiguang" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="瘦脸" prop="shoulian">
                        <el-input v-model="ruleForm.shoulian" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="时间">
                        <el-col :span="12">
                            <el-date-picker
                              v-model="ruleForm.data"
                              type="date"
                              placeholder="选择日期"
                              value-format="yyyy-MM-dd">
                            </el-date-picker>
                        </el-col>
                      </el-form-item>
                      <el-form-item label="是否补色" prop="buse">
                        <el-radio-group v-model="ruleForm.buse">
                          <el-radio label="是"></el-radio>
                          <el-radio label="否"></el-radio>
                        </el-radio-group>
                      </el-form-item>
                      <el-form-item label="地址" prop="add">
                        <el-input v-model="ruleForm.add" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="余额" prop="money">
                        <el-input v-model="ruleForm.money" class="add_input"></el-input>
                      </el-form-item>
                  </div>
                  <div style="clear:both;text-align:center;padding-top:30px;">
                      <el-form-item>
                        <el-button type="primary" @click="submitUpdate('ruleForm')">保存</el-button>
                        <el-button @click="resetForm('ruleForm')">清空</el-button>
                      </el-form-item>
                  </div>
                </el-form>
            </el-popover>
            <el-button @click="update" v-popover:popover3 type="primary" icon="el-icon-edit">修改</el-button>
            <el-popover
              ref="popover4"
              placement="bottom-start"
              width="900"
              trigger="click">
               <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="80px" size="small" class="demo-ruleForm">
                  <div style="float:left;width:350px;margin-left:100px;margin-top:30px">
                      <el-form-item label="姓名" prop="name">
                        <el-input v-model="ruleForm.name" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="电话" prop="phone">
                        <el-input v-model="ruleForm.phone" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="纹眉" prop="wenmei">
                        <el-input v-model="ruleForm.wenmei" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="美睫" prop="meijie">
                        <el-input v-model="ruleForm.meijie" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="美甲" prop="meijia">
                        <el-input v-model="ruleForm.meijia" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="脱毛" prop="tuomao">
                        <el-input v-model="ruleForm.tuomao" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="祛斑" prop="quban">
                        <el-input v-model="ruleForm.quban" class="add_input"></el-input>
                      </el-form-item>
                  </div>
                  <div style="float:left;width:350px;margin-top:30px">
                      <el-form-item label="水光" prop="shuiguang">
                        <el-input v-model="ruleForm.shuiguang" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="瘦脸" prop="shoulian">
                        <el-input v-model="ruleForm.shoulian" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="时间">
                        <el-col :span="12">
                            <el-date-picker
                              v-model="ruleForm.data"
                              type="date"
                              placeholder="选择日期"
                              value-format="yyyy-MM-dd">
                            </el-date-picker>
                        </el-col>
                      </el-form-item>
                      <el-form-item label="是否补色" prop="buse">
                        <el-radio-group v-model="ruleForm.buse">
                          <el-radio label="是"></el-radio>
                          <el-radio label="否"></el-radio>
                        </el-radio-group>
                      </el-form-item>
                      <el-form-item label="地址" prop="add">
                        <el-input v-model="ruleForm.add" class="add_input"></el-input>
                      </el-form-item>
                      <el-form-item label="余额" prop="money">
                        <el-input v-model="ruleForm.money" class="add_input"></el-input>
                      </el-form-item>
                  </div>
                  <div style="clear:both;text-align:center;padding-top:30px;">
                      <el-form-item>
                        <el-button type="primary" @click="submitForm('ruleForm')">新增</el-button>
                        <el-button @click="resetForm('ruleForm')">清空</el-button>
                      </el-form-item>
                  </div>
                </el-form>
            </el-popover>
            <el-button  v-popover:popover4 type="primary" icon="el-icon-circle-plus">增加</el-button>
            <el-button type="primary" icon="el-icon-delete" @click="delData">删除</el-button>
            <el-input placeholder="请输入内容" v-model="input5" class="input-with-select serch_input">
                <el-select style="width:130px" v-model="select" slot="prepend" placeholder="请选择">
                  <el-option label="姓名" value="1"></el-option>
                  <el-option label="电话" value="2"></el-option>
                </el-select>
                <el-button @click="search" slot="append" icon="el-icon-search"></el-button>
            </el-input>
         </div>
          <el-table
            :data="tableData"
            border
            ref="multipleTable"
            :default-sort = "{prop:'data', order: 'descending'}"
            @selection-change="handleSelectionChange"
            style="width: 100%">
            <el-table-column
              type="selection"
              width="30">
            </el-table-column>
            <el-table-column
              prop="data"
              label="日期"
              width="120"
              sortable
              style="text-align:center">
            </el-table-column>
            <el-table-column
              prop="name"
              label="姓名"
              width="120">
            </el-table-column>
            <el-table-column
              prop="phone"
              label="电话"
              width="180">
            </el-table-column>
            <el-table-column
              prop="wenmei"
              label="纹眉"
              width="120">
            </el-table-column>
            <el-table-column
              prop="meijia"
              label="美睫"
              width="120">
            </el-table-column>
            <el-table-column
              prop="meijia"
              label="美甲"
              width="120">
            </el-table-column>
            <el-table-column
              prop="tuomao"
              label="脱毛"
              width="120">
            </el-table-column>
            <el-table-column
              prop="quban"
              label="祛斑"
              width="120">
            </el-table-column>
            <el-table-column
              prop="shuiguang"
              label="水光"
              width="120">
            </el-table-column>
            <el-table-column
              prop="shoulian"
              label="瘦脸"
              width="120">
            </el-table-column>
            <el-table-column
              prop="buse"
              label="是否补色"
              :filters="[{ text: '是', value: '是' }, { text: '否', value: '否'}]"
              :filter-method="filterTag"
              filter-placement="bottom-end"
              width="60">
            </el-table-column>
            <el-table-column
              prop="add"
              label="地址">
            </el-table-column>
            <el-table-column
              prop="money"
              label="余额"
              width="120">
            </el-table-column>
          </el-table>
          <div class="block">
            <el-pagination
              @size-change="handleSizeChange"
              @current-change="handleCurrentChange"
              :current-page="curpage"
              :page-sizes="[5, 10, 15, 20]"
              :page-size="eachpage"
              layout="total, sizes, prev, pager, next, jumper"
              :total="total">
            </el-pagination>
          </div>
    </div>
</template>

<script>
import axios from 'axios';
    
  export default {
    data() {
      return {
        updateShow:true,
        addShow:false,
        tableData:[1,2],
        input5:'',
        select:'',
        searchData:{},
        curpage:1,
        total:1,
        eachpage:5,
        multipleSelection:[],
        upData:[],
        name:"",
        phone:"",
        ruleForm: {
        name: '',
        phone: '',
        data: '',
        buse:'',
        meijia:'',
        meijie:'',
        wenmei:'',
        add:'',
        tuomao:'',
        quban:'',
        shoulian:'',
        shuiguang:'',
        money:''
        },
        rules: {
          name: [
            { required: true, message: '请输入姓名', trigger: 'blur' },
            { min: 1, max: 12, message: '长度在 1 到 12 个字符', trigger: 'blur' }
          ],
          phone: [
            { required: true, message: '请输入手机号', trigger: 'blur' },
            { min: 11, max: 11, message: '11位手机号', trigger: 'blur' }
          ],
          buse: [
            { required: true, message: '请选择是否补色', trigger: 'blur' }
          ]
        }
      }
    },
    created(){
        this.getData(1,5,this.name,this.phone)
    },
    methods: {
      formatter(row, column) {
//          console.log(row,column,1)
        return row.buse;
      },
      filterTag(value, row) {
//          console.log(value,row,2)
        return row.buse == value;
      },
      handleSizeChange(val) {
//        console.log(`每页 ${val} 条`);
          this.getData(this.curpage,val,this.name,this.phone)
      },
      handleCurrentChange(val) {
//        console.log(`当前页: ${val}`);
          this.getData(val,this.eachpage,this.name,this.phone)
      },
//        选择
      handleSelectionChange(val) {
          this.multipleSelection=[];
          for(var v of val){
            this.multipleSelection.push(v._id) 
          }
//          console.log(val)
          this.upData=val;
      },
//        初始化数据
      async getData(page,rows,name,phone){
            var d=await axios.get('http://localhost:3000/yanxi/find',{params:{
                page,
                rows,
                name,
                phone
            }})
            this.tableData=d.data.rows;
            this.total=d.data.total;
            this.curpage=d.data.curpage;
            this.eachpage=d.data.eachpage;
        },
//        删除
      delData(){
            axios.get('http://localhost:3000/yanxi/del',{params:{
                ids:this.multipleSelection
            }})
                .then(function(response){
                     
//                console.log("删除成功");
                }).catch(function(err){
                        console.log(err);
                });
//                刷新表格
          this.getData(this.curpage,this.eachpage,this.name,this.phone)
          this.$message({
                      message: '姐，真替你可惜',
                      type: 'success'
                    });
        },
//        点击增加
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
//            this.ruleForm.data=this.ruleForm.data   .slice(0,11)
//              console.log(this.ruleForm.data)
            axios.get('http://localhost:3000/yanxi/add',{params:this.ruleForm})
                .then(function(response){
                     
//                console.log("增加成功");
                }).catch(function(err){
                        console.log(err);
                });
          } else {
//            console.log('error submit!!');
            return false;
          }
//                刷新表格
                this.getData(this.curpage,this.eachpage,this.name,this.phone);
                this.addShow=true;
                this.$message({
                      message: '姐，恭喜你又多一个客户',
                      type: 'success'
                    });
        });
        },
//        清空
      resetForm(formName) {
        this.$refs[formName].resetFields();
      },
//      修改
      update(){
//          console.log(this.upData.length)
          if(this.upData.length==0){
              this.updateShow=true
              this.$message({
                  message: '姐，必须至少选择一项',
                  type: 'warning'
                });
//              alert("请选择修改项")
          }else if(this.upData.length>1){
              this.updateShow=true
              this.$message({
                  message: '姐，只能同时修改一个',
                  type: 'warning'
                });
//              alert("只能同时修改一个")
          }else{
              this.updateShow=false;
              this.ruleForm=this.upData[0]
          }
        },
//        保存修改
       submitUpdate(formName){
           this.$refs[formName].validate((valid) => {
              if (valid) {
                axios.get('http://localhost:3000/yanxi/update',{params:this.ruleForm})
                    .then(function(response){
//                    console.log("保存成功");
                    
                    }).catch(function(err){
                            console.log(err);
                    });
              } else {
    //            console.log('error submit!!');
                return false;
              }
    //                刷新表格
                    this.getData(this.curpage,this.eachpage,this.name,this.phone);
                    this.updateShow=true;
                    this.$message({
                          message: '姐，修改成功',
                          type: 'success'
                        });
            });
        },
//        搜索
        async search(){
//            console.log(this.input5,this.select)
            if(this.select==1){
                this.name=this.input5;
                this.phone="";
                this.searchData={
                    name:this.input5,
                    page:this.curpage,
                    rows:this.eachpage
                }
            }else if(this.select==2){
                this.phone=this.input5;
                this.name="";
                this.searchData={
                    phone:this.input5,
                    page:this.curpage,
                    rows:this.eachpage
                }
            }
            var d=await axios.get('http://localhost:3000/yanxi/find',{params:this.searchData})
            this.tableData=d.data.rows;
            this.total=d.data.total;
            this.curpage=d.data.curpage;
            this.eachpage=d.data.eachpage;
        }
    }
}
</script>
<style scoped>
    .title_top{
        width: 100%;
        text-align: left;
        line-height: 70px;
    }
    .serch_input{
        width: 430px;
/*        outline: none;*/
  }
    .input-with-select .el-input-group__prepend {
        background-color: #fff;
  }
    .add_input{
        width: 200px;
    }
</style>