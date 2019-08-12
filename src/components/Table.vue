<template>
  <div class="table">
    <Table
      stripe
      border
      highlight-row
      :columns="columns1"
      :data="userArr"
      @on-selection-change="selBack"
    >
      <template slot-scope="{ row }" slot="id">
        <!-- <Input v-if="editIndex == index" type="text" v-model="editId" /> -->
        <span>{{ row.id }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="name">
        <Input v-if="editIndex == index" type="text" v-model="editName" />
        <span v-else>{{ row.name }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="school">
        <Input v-if="editIndex == index" type="text" v-model="editSchool" />
        <span v-else>{{ row.school }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="phone">
        <Input v-if="editIndex == index" type="text" v-model="editPhone" />
        <span v-else>{{ row.phone }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="mail">
        <Input v-if="editIndex == index" type="text" v-model="editMail" />
        <span v-else>{{ row.mail }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="username">
        <Input v-if="editIndex == index" type="text" v-model="editUsername" />
        <span v-else>{{ row.username }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="password">
        <Input v-if="editIndex == index" type="text" v-model="editPassword" />
        <span v-else>{{ row.password }}</span>
      </template>
      <template slot-scope="{ row, index }" slot="action">
        <template v-if="editIndex == index">
          <Button
            type="primary"
            style="margin-right: 5px"
            @click="determineSave(row)"
            >保存</Button
          >
          <Button @click="editIndex = -1">取消</Button>
        </template>
        <template v-else>
          <Button
            type="primary"
            ghost
            style="margin-right: 5px"
            @click="editClick(row, index)"
            >编辑</Button
          >
          <Button type="error" ghost @click="deleteRow(row, index)"
            >删除</Button
          >
        </template>
      </template>
    </Table>
  </div>
</template>

<script>
export default {
  name: 'table',
  data() {
    return {
      columns1: [
        {
          type: 'selection',
          width: 60,
          align: 'center'
        },
        {
          title: '编号',
          slot: 'id',
          align: 'center',
          sortable: true
        },
        {
          title: '姓名',
          slot: 'name',
          align: 'center'
        },
        {
          title: '学校',
          slot: 'school',
          align: 'center'
        },
        {
          title: '电话',
          slot: 'phone',
          align: 'center'
        },
        {
          title: '邮件',
          slot: 'mail',
          align: 'center'
        },
        {
          title: '账号',
          slot: 'username',
          align: 'center'
        },
        {
          title: '密码',
          slot: 'password',
          align: 'center'
        },
        {
          title: '操作',
          slot: 'action',
          align: 'center'
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped></style>
