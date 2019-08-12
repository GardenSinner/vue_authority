<template>
  <div class="drawer">
    <Drawer
      title="添加用户"
      :closable="true"
      v-model="value"
      width="15"
      :mask-closable="false"
    >
      <div class="item">
        <Input
          v-model="addName"
          placeholder="填写姓名"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">姓名：</span>
        </Input>
      </div>
      <div class="item">
        <Input
          v-model="addSchool"
          placeholder="填写学校"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">学校：</span>
        </Input>
      </div>
      <div class="item">
        <Input
          v-model="addPhone"
          placeholder="填写手机"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">手机：</span>
        </Input>
      </div>
      <div class="item">
        <Input
          v-model="addMail"
          placeholder="填写邮件"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">邮件：</span>
        </Input>
      </div>
      <div class="item">
        <Input
          v-model="addUsername"
          placeholder="填写账号"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">账号：</span>
        </Input>
      </div>
      <div class="item">
        <Input
          v-model="addPassword"
          placeholder="填写密码"
          clearable
          style="width: 220px"
        >
          <span slot="prepend">密码：</span>
        </Input>
      </div>
      <Button type="success" long style="margin-top: 20px" @click="useaddUser"
        >确认提交</Button
      >
      <Button type="error" long style="margin-top: 20px" @click="value = false"
        >取消</Button
      >
    </Drawer>
  </div>
</template>

<script>
export default {
  name: 'drawer',
  data() {
    return {
      value: false,
      addId: '',
      addName: '',
      addSchool: '',
      addPhone: '',
      addMail: '',
      addUsername: '',
      addPassword: ''
    };
  },
  methods: {
    useaddUser() {
      this.$emit('addUser');
    }
  }
};
</script>

<style lang="scss" scoped>
.item {
  margin-bottom: 10px;
}
</style>
