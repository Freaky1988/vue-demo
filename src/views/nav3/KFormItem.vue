<template>
    <div>
        <label v-if="label">{{label}}</label>
        <!--input占位符-->
        <slot></slot>
        <!-- 错误信息展示 -->
        <p v-if="error">
            {{error}}
        </p>
    </div>
</template>

<script type="text/javascript">
    export default{
        inject:['form'],
        data(){
            return{
                error:""
            }
        },
        props:{
            label:{
                type:String,
                default:""
            }
        },
        mounted(){
            //监听校验事件
            this.$on('validate',this.validate)
        },
        methods:{
            validate(){
                //施行具体的校验
                //1.获取校验规则
                console.dir(this.form.rules);
                //2.获取数据模型
                console.log(this.form.model);
            }
        }
    }
</script>

<style>
    
</style>