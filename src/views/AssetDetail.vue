<template>
    <Row>
        选择币种：
        <el-select v-model="coins" filterable placeholder="请选择" style="margin-right: 20px">
            <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        选择交易所：
        <el-select v-model="exchange" filterable placeholder="请选择">
            <el-option
                    v-for="item in option1"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        <Tabs type="card" style="margin-top: 30px">
            <TabPane label="全部">
                <Table border :columns="columns1" :data="data1"></Table>
                <Page :total="100" show-elevator style="display: flex;justify-content: center;margin-top: 10px" v-show="!hideCount"></Page>
            </TabPane>
            <TabPane label="充值">充值</TabPane>
            <TabPane label="提现">提现</TabPane>
            <TabPane label="交易">交易</TabPane>
            <TabPane label="其他">其他</TabPane>
        </Tabs>

    </Row>

</template>
<script>
    import * as apiRequest from '../api/api'
    import { FormatData } from '../api/time'
    import axios from 'axios'
    export default {
      data() {
        return {
          exchange: '',
          coins: '',
          options: [],
          option1: [],
          value8: '',
          hideCount: true,
          columns1: [
            {
              title: '时间',
              key: 'createTime',
              render: function (h, params) {
                return h('div',
                  FormatData(new Date(this.row.createTime),'yyyy-MM-dd hh:mm:ss'))
                /*这里的this.row能够获取当前行的数据*/
              }
            },

            {
              title: '资金变动方向',
              key: 'side'
            },
            {
              title: '发生额',
              key: 'amount'
            },
            {
              title: '变动后的余额',
              key: 'balance'
            },
            {
              title: '类型',
              key: 'type'
            },
            {
              title: '备注',
              key: 'remark'
            }
          ],
          data1: []
        }
      },
      mounted() {
        // this.initFormatter();
        this.getCoinsList();
        this.getAllExchangeList();
        this.getAssetsDetail();
      },
      methods: {
        //获取所有币种
        getCoinsList() {
          apiRequest.getAllCurrency({
            token: 'add61ab01f8a36a0fb2a1eb3375a6085'
          }).then(
            data => {
              console.log(data)
              if (data.code == 0) {
                this.options = data.data.map((item, index) => {
                  return {value: index, label: item}
                })
              }
            })
        },
        //获取所有交易所
        getAllExchangeList() {
          apiRequest.getAllExchange({
            token: 'add61ab01f8a36a0fb2a1eb3375a6085'
          }).then(
            data => {
              console.log(data)
              if (data.code == 0) {
                this.option1 = data.data.map(item => {
                  return {value: item.exId, label: item.exName}
                })
              }
            }
          )
        },
        //获取详情
        getAssetsDetail() {
          apiRequest.AssetsDetail({
            token: 'add61ab01f8a36a0fb2a1eb3375a6085'
          }).then(
            data => {
              this.data1 = data.data}
            )
        }}}
</script>
