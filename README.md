# VuePlugin

平常自己开发过程当中抽离出来的Vue插件集合

> [git](https://github.com/ishareme/VuePlugin)

> [npm 还没]()

## Example

[example 还没]()

## Validate 验证插件
> [link](https://github.com/ishareme/VuePlugin/tree/master/Validate)

#### Basic Usage

##### v-model的值、rules对象的key、$validate的值必须保持一致

```
import validate from './plugin/validate'

Vue.use(validate)

data(){
       return {
               account: 'xxx',
               passWord: '',
       
               rules: {
                   account: {
                          require: true,
                          isString: true,
                          validator: () => {
       
                          },
                   },
                   passWord: {
                          require: true,
                   }
               }
       }
},

//验证账户和密码
this.$validate('account').then(data => {
                    return this.$validate('passWord')
                }).then(() => {
                    //异步操作
                    xxxx
                }).catch((err) => {
                    console.log(err)
                })
```
 
 #### Options
 
  |Option|Description 
  |----- |---------- 
  |require|Boolean  是否是必填选项  
  |isEmail|Boolean 是否是邮箱   
  |isIp|Boolean 是否是Ip地址    
  |isTel| Boolean  是否是电话   
  |isPhone| Boolean  是否是手机号     
  |isEnglish| Boolean  是否是英文    
  |isChinese| Boolean    是否是中文   
  |isNumber|Boolean 是否是数字 
  |isString|Boolean 是否是字符串
  |isIdentityNum|Boolean 是否是身份证 
  |min|Number 最小值 
  |max|Number 最大值 
  |minLength|String or Number  最小长度 
  |maxLength|String or Number  最大长度  
  |isPassWord|Boolean  验证密码 (6-16位, 数字, 字母, 字符至少包含两种, 同时不能包含中文和空格)
