<template>
    <div>
        <FormItem 
            :label="label" 
            :label-width="labelWidth"
            :label-for="labelFor"
            :show-message="showMessage"
            :rules="rules.rules1" 
            :prop="prop"
            v-if="rules.rules1.condition" 
            :class="[rules.rules1.required ? '' : 'ivu-form-item-font']" 
           
        >
            <slot name="form-element"></slot>
        </FormItem>
        <FormItem 
            :label="label" 
            :label-width="labelWidth"
            :label-for="labelFor"
            :show-message="showMessage"
            :rules="rules.rules2" 
            :prop="prop"
            v-if="rules.rules2.condition" 
            :class="[rules.rules2.required ? '' : 'ivu-form-item-font']" 
            
        >
            <slot name="form-element"></slot>
        </FormItem>
    </div>
</template>

<script>
    import { FormItem } from 'iview'
    export default {
        props: {
            label: String,
            labelWidth: Number,
            labelFor: String,
            showMessage: Boolean,
            prop: String,
            rules: Object
        },
        components: {
            FormItem
        }
    }
</script>

<style>
    .ivu-form-item-font .ivu-form-item-label::before {
        content: '*';
        display: inline-block;
        margin-right: 4px;
        line-height: 1;
        font-family: SimSun;
        font-size: 12px;
        visibility: hidden;
    }
</style>
