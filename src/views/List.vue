<template>
    <el-row>
        <el-col :span="24">
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                    <span>案件一覧</span>
                </div>
                <div>...</div>
            </el-card>
        </el-col>
    </el-row>
</template>

<script>
 /* eslint-disable no-console */

  import axios from 'axios'

  export default {
    name: "Currency",
    data () {
      return {
        currencies: []
      }
    },
    created: async function () {
      await this.refresh()
    },
    methods: {
      refresh: async function () {
        const res = await axios.get('http://localhost:8080/')
        this.currencies = res.data.currencies
        console.info(this.currencies)
      }
    }
  }
</script>

<style scoped>

</style>