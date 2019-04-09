<template>
	<div>
		<el-form :model="form" label-width="80px" :rules="rules" ref="loginForm" style="margin:20px;width:60%;min-width:600px;">
			<el-form-item label="用户名" prop="username">
				<el-input v-model="form.username"></el-input>
			</el-form-item>
			<el-form-item label="用户密码" prop="password">
				<el-input type="password" v-model="form.password"></el-input>
			</el-form-item>
			<el-form-item>
				<el-button type="primary" @click="submitForm('loginForm')">提交</el-button>
			</el-form-item>
		</el-form>

		<h2>自制input测试</h2>
		<hr>
		<k-form :model="form" :rules="rules" ref="KloginForm">
			<k-form-item label="用户名">
				<k-input v-model="form.username"></k-input>
			</k-form-item>
			<k-form-item label="密码">
				<k-input type="password" v-model="form.password"></k-input>
			</k-form-item>
		</k-form>
	</div>

</template>

<script>
	import KInput from "./KInput.vue"
	import KFormItem from "./KFormItem.vue"
	import KForm from "./KForm.vue"
    export default {
	    components:{
            KInput,
            KFormItem,
            KForm
		},
        data() {
            return {
                form: {
                    username: '',
                    password: ''
                },
				rules:{
                    username:[{required:true,message:"请输入用户名！"}],
                    password:[{required:true,message:"请输入密码！"}],
				}
            }
        },
        methods: {
            submitForm(form) {
                this.$refs[form].validate(valid=>{
                    if(valid){
						alert("成功")
					}else{
                        alert("失败")
					}
				})
            }
        }
    }

</script>