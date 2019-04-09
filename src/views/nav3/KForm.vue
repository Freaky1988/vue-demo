<template>
    <form>
        <slot></slot>
    </form>
</template>

<script type="text/javascript">
    export default{
        provide(){
            //把表单实例作为参数传递下去，子代可以直接使用
            return{
              form:this
            }
        },
        data(){
            return{
                prop:[]
            }
        },
        props:{
            model:{
                type:Object,
                required:true
            },
            rules:{
                type:Object,
            }
        }
    }
</script>

<style>
    
</style>