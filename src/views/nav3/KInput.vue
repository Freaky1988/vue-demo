<template>
    <div>
        <input :type="type" :value="value" @input="onInput">
    </div>
</template>

<script>
    export default {

        props:{
            value:{
                type:String,
                default:""
            },
            type:{
                type:String,
                default:""
            }
        },
        methods:{
            onInput(e){
                //派发事件
                this.$emit('input',e.target.value)
                this.$parent.$emit('validate')
            }
        }
    }

</script>