<template>
    <div>
        选择币种：
        <el-select v-model="value8" filterable placeholder="请选择" style="margin-right: 20px">
            <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        选择交易所：
        <el-select v-model="value8" filterable placeholder="请选择">
            <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        选择币种：
        <el-select v-model="value8" filterable placeholder="请选择" style="margin-right: 20px">
            <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        选择交易所：
        <el-select v-model="value8" filterable placeholder="请选择">
            <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
            </el-option>
        </el-select>
        <div style="width: auto;overflow-x: auto;white-space: nowrap;height: 800px;clear: both">
            <div style="width: auto;clear: both">
                <ul style="line-height: 40px;height: 40px;background: rgb(248,248,248);clear: both;font-size: 12px;font-weight: 700;color: #495060;" class="uul">
                    <li style="width: 200px;text-align: center">时间</li>
                    <li style="width: 100px;text-align: center">交易类型</li>
                    <li style="width: 100px;text-align: center">交易对</li>
                    <li style="width: 100px;text-align: center">方向</li>
                    <li style="width: 100px;text-align: center">价格</li>
                    <li style="width: 100px;text-align: center">委托量</li>
                    <li style="width: 100px;text-align: center">已经成交</li>
                    <li style="width: 100px;text-align: center">成交均价</li>
                    <li style="width: 100px;text-align: center">状态</li>
                    <!--<li style="width: 100px;text-align: center">机构订单ID</li>-->
                    <!--<li style="width: 100px;text-align: center">机构用户ID</li>-->
                    <li style="width: 150px;text-align: center"></li>
                </ul>
            </div>
            <ul style="clear: both">
                <li style="width: 100%;height: auto;border-top: 1px solid #e9eaec;display: flex;flex-direction: column;background: white;clear: both">
                <div style="clear: both">
                    <div style="width: auto;clear: both">
                        <ul style="line-height: 50px;height: 50px;background: rgb(255,255,255);clear: both" class="uul">
                            <li style="width: 200px;text-align: center">2018.03.01 - 2019.09.03</li>
                            <li style="width: 100px;text-align: center">杠杆交易</li>
                            <li style="width: 100px;text-align: center">BTC-EOS</li>
                            <li style="width: 100px;text-align: center">方向</li>
                            <li style="width: 100px;text-align: center">87</li>
                            <li style="width: 100px;text-align: center">1000</li>
                            <li style="width: 100px;text-align: center">800</li>
                            <li style="width: 100px;text-align: center">87</li>
                            <li style="width: 100px;text-align: center">成功</li>
                            <!--<li style="width: 100px;text-align: center">878776</li>-->
                            <!--<li style="width: 100px;text-align: center">879985</li>-->
                            <li style="width: 150px;text-align: center" @click="a*=-1">详情
                                <i class="el-icon-arrow-down" :class="[a==1?'el-icon-arrow-up go':'el-icon-arrow-down aa']"></i>
                            </li>
                        </ul>
                    </div>

                </div>
                <div style="clear: both">
                    <ul style="display: flex;flex-direction: column;clear: both;background: rgb(248,248,248)" class="huzi-ul" v-show="a==1">
                        <li>
                            <ul style="display: flex;flex-direction: row;clear: both;">
                                <li>时间</li>
                                <li>价格</li>
                                <li>数量</li>
                                <li>成交额</li>
                                <li>手续费</li>
                            </ul>
                        </li>
                        <li>
                            <ul style="display: flex;flex-direction: row">
                                <li>2018-07-04 16:27:47</li>
                                <li>6530.5</li>
                                <li>0.00001</li>
                                <li>0.00001</li>
                                <li>0.5678765BTC</li>
                            </ul>
                        </li>
                        <li>
                            <ul style="display: flex;flex-direction: row">
                                <li>2018-07-04 16:27:47</li>
                                <li>6530.5</li>
                                <li>0.00001</li>
                                <li>0.00001</li>
                                <li>0.5678765BTC</li>
                            </ul>
                        </li>
                        <li>
                            <ul style="display: flex;flex-direction: row">
                                <li>2018-07-04 16:27:47</li>
                                <li>6530.5</li>
                                <li>0.00001</li>
                                <li>0.00001</li>
                                <li>0.5678765BTC</li>
                            </ul>
                        </li>
                    </ul>
                </div>
                </li>



            </ul>
        </div>
    </div>
</template>
<style scoped>
    li{
        list-style: none;
    }
    .uul li{
            float: left;
    }
    .huzi-ul li{
        width: 100%;

    }
    .huzi-ul{
        clear: both;
    }
    .aa{
        transition: all 1s;
    }
    .go{
        transform:rotateY(180deg);
        transition: all 1s;
    }

</style>
<script>
  import expandRow from './table-expand.vue';
  export default {
    components: { expandRow },
    data () {
      return {
        a:-1,
        b:-1,
        options: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶'
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        value8: '',
        columns8: [
          {
            "title": "时间",
            "key": "name",
            // "fixed": "left",
            "width": 170
          },
          {
            "title": "交易类型",
            "key": "show",
            "width": 100,
            // "sortable": true,
            // filters: [
            //   {
            //     label: 'Greater than 4000',
            //     value: 1
            //   },
            //   {
            //     label: 'Less than 4000',
            //     value: 2
            //   }
            // ],
            // filterMultiple: false,
            // filterMethod (value, row) {
            //   if (value === 1) {
            //     return row.show > 4000;
            //   } else if (value === 2) {
            //     return row.show < 4000;
            //   }
            // }
          },
          {
            "title": "交易对",
            "key": "weak",
            "width": 100,
          },
          {
            "title": "方向",
            "key": "signin",
            "width": 100,
          },
          {
            "title": "价格",
            "key": "click",
            "width": 100,
          },
          {
            "title": "委托量",
            "key": "active",
            "width": 100,
          },
          {
            "title": "已成交",
            "key": "day7",
            "width": 100,
          },
          {
            "title": "成交均价",
            "key": "day30",
            "width": 100,
          },
          {
            "title": "状态",
            "key": "tomorrow",
            "width": 100,
          },
          // {
          //   "title": "机构订单ID",
          //   "key": "day",
          //   "width": 100,
          // },
          // {
          //   "title": "机构用户ID",
          //   "key": "week",
          //   "width": 100,
          // },
          {
            // "fixed": "right",
            key: 'action',
            width: 100,
            align: 'right',
            render: (h, params) => {
              return h('div', [
                h('p', {
                  props: {
                    type: 'primary',
                    size: 'small'
                  },
                  style: {
                    marginRight: '5px',
                    textAlign:'right'
                  },
                  on: {
                    click: () => {
                      this.show(params.index)
                    }
                  }
                }, '查看详情'),
              ]);
            },
          },
          {
            type: 'expand',
            width: 20,
            align: 'left',
            render: (h, params) => {
              return h(expandRow, {
                props: {
                  row: params.row
                },
                style: {
                  textAlign: 'left'
                },
              },'查看详情')

            },
          },

        ],
        data7: [
          {
            "name": "2017.07.09 - 2018.02.02",
            "fav": 0,
            "show": 7302,
            "weak": 5627,
            "signin": 1563,
            "click": 4254,
            "active": 1438,
            "day7": 274,
            "day30": 285,
            "tomorrow": 1727,
            "day": 558,
            "week": 4440,
            "month": 5610
          },
          {
            "name": "Name2",
            "fav": 0,
            "show": 4720,
            "weak": 4086,
            "signin": 3792,
            "click": 8690,
            "active": 8470,
            "day7": 8172,
            "day30": 5197,
            "tomorrow": 1684,
            "day": 2593,
            "week": 2507,
            "month": 1537
          },
          {
            "name": "Name3",
            "fav": 0,
            "show": 7181,
            "weak": 8007,
            "signin": 8477,
            "click": 1879,
            "active": 16,
            "day7": 2249,
            "day30": 3450,
            "tomorrow": 377,
            "day": 1561,
            "week": 3219,
            "month": 1588
          },
          {
            "name": "Name4",
            "fav": 0,
            "show": 9911,
            "weak": 8976,
            "signin": 8807,
            "click": 8050,
            "active": 7668,
            "day7": 1547,
            "day30": 2357,
            "tomorrow": 7278,
            "day": 5309,
            "week": 1655,
            "month": 9043
          },
          {
            "name": "Name5",
            "fav": 0,
            "show": 934,
            "weak": 1394,
            "signin": 6463,
            "click": 5278,
            "active": 9256,
            "day7": 209,
            "day30": 3563,
            "tomorrow": 8285,
            "day": 1230,
            "week": 4840,
            "month": 9908
          },
          {
            "name": "Name6",
            "fav": 0,
            "show": 6856,
            "weak": 1608,
            "signin": 457,
            "click": 4949,
            "active": 2909,
            "day7": 4525,
            "day30": 6171,
            "tomorrow": 1920,
            "day": 1966,
            "week": 904,
            "month": 6851
          },
          {
            "name": "Name7",
            "fav": 0,
            "show": 5107,
            "weak": 6407,
            "signin": 4166,
            "click": 7970,
            "active": 1002,
            "day7": 8701,
            "day30": 9040,
            "tomorrow": 7632,
            "day": 4061,
            "week": 4359,
            "month": 3676
          },
          {
            "name": "Name8",
            "fav": 0,
            "show": 862,
            "weak": 6520,
            "signin": 6696,
            "click": 3209,
            "active": 6801,
            "day7": 6364,
            "day30": 6850,
            "tomorrow": 9408,
            "day": 2481,
            "week": 1479,
            "month": 2346
          },
          {
            "name": "Name9",
            "fav": 0,
            "show": 567,
            "weak": 5859,
            "signin": 128,
            "click": 6593,
            "active": 1971,
            "day7": 7596,
            "day30": 3546,
            "tomorrow": 6641,
            "day": 1611,
            "week": 5534,
            "month": 3190
          },
          {
            "name": "Name10",
            "fav": 0,
            "show": 3651,
            "weak": 1819,
            "signin": 4595,
            "click": 7499,
            "active": 7405,
            "day7": 8710,
            "day30": 5518,
            "tomorrow": 428,
            "day": 9768,
            "week": 2864,
            "month": 5811
          }
        ]
      }
    },
    methods: {
      exportData (type) {
        if (type === 1) {
          this.$refs.table.exportCsv({
            filename: 'The original data'
          });
        } else if (type === 2) {
          this.$refs.table.exportCsv({
            filename: 'Sorting and filtering data',
            original: false
          });
        } else if (type === 3) {
          this.$refs.table.exportCsv({
            filename: 'Custom data',
            columns: this.columns8.filter((col, index) => index < 4),
            data: this.data7.filter((data, index) => index < 4)
          });
        }
      }
    }
  }
</script>