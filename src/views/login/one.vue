<template>
  <div>
    <el-button v-text="$t('sceneHome.start')"></el-button>
	<el-button>{{$t('sceneHome.start')}}</el-button>
   <el-dropdown trigger="click" class="international" @command="handleSetLanguage">
    <div>
       <!--<svg-icon class-name="international-icon" icon-class="language" />-->
       <i class="el-icon-s-tools"></i>
     </div>
     <el-dropdown-menu slot="dropdown">
       <el-dropdown-item :disabled="language==='zh'" command="zh">
         中文
       </el-dropdown-item>
       <el-dropdown-item :disabled="language==='en'" command="en">
         English
       </el-dropdown-item>
     </el-dropdown-menu>
   </el-dropdown>
  </div>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  name: 'Dashboard',
   data() {
      return{
        ruleForm: {
          name: '1',
        },
        rules: {
          name: [
            { required: true, message: this.$t('sceneEdit.formNameTip'), trigger: 'blur' }
          ],
        }
      }
    },
  computed: {
  },
  methods: {
    getTitle(title){
        let str = 'lang.'+title;
        return this.$t(str);
    },
    handleSetLanguage(lang) {
      console.log(lang);
      Cookies.set('language' ,lang)
   this.$i18n.locale = lang
  },
}
}
</script>

<style lang="scss" scoped>
</style>
