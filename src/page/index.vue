<template>
  <div>
    <table class="table table-striped table-bordered">
      <thead>
      <tr>
          <th width=15%>序号</th>
          <th width=17% >id</th>
          <th width=17% >内容</th>
      </tr> 
      </thead>
      <tbody>
          <tr v-for="(item,index) in selectList">
              <td class="center">{{index+1}}</td>
              <td class="center">{{item.id}}</td>
              <td class="center">{{item.content}}</td>
          </tr> 
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data(){
          return{
                selectList:[]
            }
        },
  created () {
    this.$api.get('topics', null, r => {
      console.log(r)
      this.selectList=r.data

    })
  }
}
</script>