<template>
  <div class="componentDetails">11
    <div class="componentDetails-left" id="componentDetails-left">333
      <el-input :placeholder="$t('m.componentDetails16')" v-model="filterText"></el-input>

      <el-tree class="filter-tree" :data="figureGroupTree" :props="defaultProps" :default-expand-all="false" :filter-node-method="filterNode" @node-click="handleNodeClick" :highlight-current="true" node-key="label" :default-expanded-keys="idArr" ref="tree2">
      </el-tree>
    </div>
    <div class="componentDetails-resize componentDetails-resize1" ref="resize1" id="resize"></div>
    <div class="componentDetails-mid" id="componentDetails-mid">
      <div class="ipcFigureUrlList" v-for="(item, index) in ipcFigureUrlList" :key="index">
        <i class="el-icon-picture-outline"></i>
        <span class="ipcFigureUrlList-name" @click="showIpc(item)">{{ item.ipcFigureName }}</span>
      </div>
      <el-table :data="partPositionInfoList" border style="width: 100%;margin-top: 3px;" :empty-text="$t('m.zwsj')">
        <el-table-column prop="itemInfo" label="ITEM" width="60">
          <template slot-scope="scope">
            <span class="toDetails" @click="editCurrentApplicationApproval(scope.row)">{{ scope.row.itemInfo ? scope.row.itemInfo : '--' }}</span>
          </template>
        </el-table-column>
        <el-table-column prop="partNumber" label="PART NUMBER" width="140">
          <template slot-scope="scope">
            <span class="toDetails" @click="showDetails(scope.row)">{{ scope.row.partNumber ? scope.row.partNumber : '--' }}</span>
            <el-tooltip class="item" effect="dark" :content="`${$t('m.componentDetails17')}${scope.row.parentItem}）`" placement="top-start" v-if="scope.row.parentItem">
              <svg style="position: absolute;right: 5px;top: 2px;" t="1639383400433" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="1709" width="20" height="20">
                <path d="M512 899.5c-213.668 0-387.5-173.832-387.5-387.5S298.332 124.5 512 124.5 899.5 298.332 899.5 512 725.668 899.5 512 899.5z" fill="#4472C4" p-id="1710"></path>
                <path d="M512 137c-206.776 0-375 168.224-375 375s168.224 375 375 375 375-168.224 375-375-168.224-375-375-375m0-25c220.914 0 400 179.086 400 400S732.914 912 512 912 112 732.914 112 512s179.086-400 400-400z" fill="#4472C4" p-id="1711"></path>
                <path d="M660.242 602.86c0-5.225-2.9-9.289-8.128-12.772-5.225-2.9-10.45-4.644-15.675-4.644a23.185 23.185 0 0 0-10.449 2.316 24.747 24.747 0 0 0-6.967 6.386 120.621 120.621 0 0 0-8.708 11.614c-3.483 4.064-6.386 7.547-9.869 11.03a266.264 266.264 0 0 1-22.646 21.48 217.009 217.009 0 0 1-28.447 18.578 142.515 142.515 0 0 1-31.35 12.772 108.539 108.539 0 0 1-32.511 5.225 65.613 65.613 0 0 1-26.125-5.225 52.483 52.483 0 0 1-23.222-17.417c-6.967-6.967-12.772-16.836-16.836-29.028-4.64-11.615-6.382-26.124-6.382-42.96 0-10.45 0-22.641 1.161-35.994 1.162-12.773 2.323-24.961 3.484-35.995 3.483-24.966 8.708-47.605 16.255-68.505 6.967-19.739 15.094-37.155 24.383-51.089s19.158-24.964 29.608-33.091c10.45-7.547 20.319-11.611 30.189-11.611 4.644 0 9.289 1.161 13.933 2.322a122.842 122.842 0 0 1 12.192 6.386 159.436 159.436 0 0 1 15.094 12.772c4.644 4.644 9.289 9.869 13.353 14.514 2.322 4.064 4.644 6.967 6.967 8.128a22.966 22.966 0 0 0 8.708 5.806c2.322 1.742 5.225 2.322 8.708 2.322a31.6 31.6 0 0 0 15.675-4.064c4.644-2.9 7.547-6.967 7.547-12.772a12.978 12.978 0 0 0-1.742-5.806l-2.322-4.644c-5.806-6.386-12.192-12.772-19.158-19.739a192.781 192.781 0 0 0-24.383-18.578 180.879 180.879 0 0 0-28.447-13.353 89.266 89.266 0 0 0-30.189-5.225 97.223 97.223 0 0 0-38.9 8.128c-12.772 5.806-23.222 12.192-31.93 20.319a176.977 176.977 0 0 0-37.733 49.348 322.674 322.674 0 0 0-24.963 60.377c-6.387 22.061-11.031 43.542-13.353 65.022A454.327 454.327 0 0 0 363 574.409a184.567 184.567 0 0 0 3.483 35.994 112.024 112.024 0 0 0 10.45 34.257 106.673 106.673 0 0 0 21.48 30.189 110.071 110.071 0 0 0 33.091 23.8c17.417 9.289 36.575 13.353 57.475 13.353 22.061 0 41.219-2.9 58.636-8.708a193.1 193.1 0 0 0 46.445-23.224 192.039 192.039 0 0 0 35.994-32.51c9.869-11.611 18.578-23.222 26.705-34.833l2.322-4.644a11.592 11.592 0 0 0 1.161-5.223z" fill="#FFFFFF" p-id="1712"></path>
              </svg>
            </el-tooltip>
          </template>
        </el-table-column>
        <el-table-column prop="nomenclatureList" label="NOMENCLATURE" width="200" show-overflow-tooltip>
          <template slot-scope="scope">
            <span class="zi" v-if="scope.row.itemLayer === 1 || scope.row.itemLayer === 2"></span>
            <span class="zi2" v-if="scope.row.itemLayer === 2"></span>
            <span v-for="(item,index) in scope.row.nomenclatureList" :key="item.partNomenclatureId">{{ item.nomenclature }}<span v-if="index != scope.row.nomenclatureList.length-1">,</span></span>
          </template>
        </el-table-column>
        <el-table-column prop="cageCode" label="CAGECODE" width="100">
          <template slot-scope="scope">
            {{ scope.row.cageCode ? scope.row.cageCode : '--' }}
          </template>
        </el-table-column>
        <el-table-column width="130">
          <template slot="header">
            <div>UNITS PER ASSY</div>
          </template>
          <template slot-scope="scope">
            {{ scope.row.unitsPerAssy ? scope.row.unitsPerAssy : '--' }}
          </template>
        </el-table-column>
        <el-table-column width="110">
          <template slot="header">
            USAGE CODE
          </template>
          <template slot-scope="scope">
            {{ scope.row.usageCode ? scope.row.usageCode : '--' }}
          </template>
        </el-table-column>
        <el-table-column prop="quantity" label="remark">
          <template slot-scope="scope">
            <el-tooltip placement="top">
              <div slot="content" v-html="scope.row.remark ? huanhang(scope.row.remark) : '--'"></div>
              <div v-html="scope.row.remark ? huanhang(scope.row.remark) : '--'" style="overflow: hidden;text-overflow: ellipsis; display: -webkit-box;-webkit-line-clamp: 2;-webkit-box-orient: vertical;"></div>
            </el-tooltip>
          </template>
        </el-table-column>
      </el-table>
    </div>
    <div class="componentDetails-resize componentDetails-resize2" ref="resize2" id="resize2"></div>
    <div class="componentDetails-right" id="componentDetails-right" style="position: relative;">
      <div id="test" style="width: 100%;height: 100%;background-color: transparent;position: absolute;top: 0;left: 0;z-index: -1;"></div>
      <!--      <el-button @click="loadPdf" type="primary" style="height: 37px;text-align: center;display: block;margin: 0 auto;margin-top: 50%" v-if="!ifLoadPdf && ifDetails">加载手册</el-button>-->
      <iframe style="width: 100%;height: 100%;" id="mineIframe" :src="pdfUrl" v-if="(ifLoadPdf && ifDetails) || true"></iframe>
      <!--      <embed-->
      <!--        v-if="ifLoadPdf && ifDetails && (pdfUrl.indexOf('.SVG') >= 0 || pdfUrl.indexOf('.svg') >= 0)"-->
      <!--        style="width: 100%;height: 100%;overflow-y: auto;"-->
      <!--        :src="svgVal"-->
      <!--        type="image/svg+xml"-->
      <!--        pluginspage="http://www.adobe.com/svg/viewer/install/" />-->
    </div>
    <!--    商品详情弹框-->
    <el-dialog
      custom-class="productDetails"
      :title="$t('m.spxq')"
      :visible.sync="dialogVisible"
      width="90%"
      v-dialogDrag
      :close-on-press-escape="false"
      :close-on-click-modal="false">
      <product-details ref="productDetails"></product-details>
    </el-dialog>
  </div>
</template>
<script>
import { getToken } from '@/utils/auth'
import { huanhang } from '@/utils'
import { getFigureGroupTree, getPartPositionInfoList } from '@/api/allAPi'
import { Message } from 'element-ui'
import productDetails from '@/views/dashboard/productDetails'
export default {
  data() {
    return {
      ipcFigureUrlList: [],
      svgVal: '', // http://192.168.16.50/static/N_PC_112134_04_A_01_01.SVG
      currentPartId: '',
      ifDetails: false,
      ifLoadPdf: false,
      dialogVisible: false,
      filterText: '',
      figureGroupTree: [],
      defaultProps: {
        children: 'children',
        label: 'label'
      },
      partPositionInfoList: [],
      pdfUrl: '',
      idArr: []
    }
  },
  mounted() {
    if (this.$route.query.figureGroup) {
      this.figureGroup = decodeURI(this.$route.query.figureGroup)
      this.getFigureGroupTree()
    }
    if (this.$route.query.eipcFigureInfoId) {
      this.handleNodeClick({ eipcFigureInfoId: this.$route.query.eipcFigureInfoId })
    }
    this.dragControllerDiv()
    this.dragControllerDiv2()
  },
  watch: {
    filterText(val) {
      this.$refs.tree2.filter(val)
    }
  },
  methods: {
    showIpc(item) {
      this.pdfUrl = item.ipcFigureUrl + '?token=' + getToken()
      this.ifLoadPdf = true
      this.ifDetails = true
      this.$nextTick(() => {
        // document.getElementById('mineIframe').contentWindow.document.getElementsByTagName('svg').style.width = '100%'
      })
    },
    huanhang(val) {
      return huanhang(val)
    },
    editCurrentApplicationApproval(row) {
      // 获取pdf地址
      this.pdfUrl = '/hrmgr/eipcFigureInfo/previewFigureFile?eipcFigureInfoId=' + row.eipcFigureInfoId + '&token=' + getToken() + '&pageNumber=' + row.pageNumber
      console.log(row.pageNumber, row.eipcFigureInfoId)
      this.ifLoadPdf = true
      this.ifDetails = true
    },
    // 商品详情
    showDetails(item) {
      console.log(item)
      if (item.partId) {
        this.dialogVisible = true
        this.$nextTick(() => {
          this.$refs.productDetails.initData(item.partId)
        })
      } else {
        Message({
          message: this.$t('m.field07'),
          type: 'error',
          duration: 2 * 1000,
          showClose: true
        })
      }
    },
    loadPdf() {
      this.ifLoadPdf = true
    },
    // 产品树点击事件
    handleNodeClick(data) {
      this.svgVal = 'http://192.168.16.50/static/N_PC_112134_04_A_01_01.SVG'
      if (data.eipcFigureInfoId) {
        this.ifDetails = true
        this.ifLoadPdf = false
        // 产品树详情页
        this.loadingShow()
        getPartPositionInfoList({ eipcFigureInfoId: data.eipcFigureInfoId }).then(res => {
          this.partPositionInfoList = res.data.partPositionList
          this.ipcFigureUrlList = res.data.ipcFigureUrlList
        })
        // 获取pdf地址
        this.pdfUrl = '/hrmgr/eipcFigureInfo/previewFigureFile?eipcFigureInfoId=' + data.eipcFigureInfoId + '&token=' + getToken()
      }
    },
    // 产品树详情树
    getFigureGroupTree() {
      const self = this
      setTimeout(() => {
        this.loadingShow()
        getFigureGroupTree({ partsTreeId: this.figureGroup }).then(res => {
          this.figureGroupTree = res.data
          self.figureGroupTree.forEach(m => {
            self.idArr.push(m.label)
          })
          if (this.$route.query.label) {
            self.idArr.push(this.$route.query.label)
            self.$nextTick(() => {
              self.$refs.tree2.setCurrentKey(this.$route.query.label)// 获取已经设置的资源后渲染
            })
          }
        })
      }, 300)
    },
    filterNode(value, data) {
      if (!value) return true
      return data.label.indexOf(value) !== -1
    },
    // 左边拉宽条调整宽度
    dragControllerDiv: function () {
      // 保留this引用
      const resize = document.getElementById('resize')
      resize.onmousedown = function (e) {
        // 颜色改变提醒
        resize.style.background = '#818181'
        let startX = e.clientX
        resize.left = resize.offsetLeft
        document.onmousemove = function (e) {
          // 计算并应用位移量
          const endX = e.clientX
          startX = endX
          // let lfetWidth = document.body.clientWidth - document.getElementById('componentDetails-right').clientWidth - 20
          // let lfetWidth2 = document.getElementById('componentDetails-left').clientWidth
          document.getElementById('componentDetails-left').style.width = endX + 'px'
          document.getElementById('componentDetails-mid').style.width =
            (document.body.clientWidth - document.getElementById('componentDetails-left').clientWidth -
              document.getElementById('componentDetails-right').clientWidth - 10) + 'px'
        }
        document.onmouseup = function () {
          // 颜色恢复
          resize.style.background = ''
          document.onmousemove = null
          document.onmouseup = null
        }
        return false
      }
    },
    // 右边拉宽条调整宽度
    dragControllerDiv2: function () {
      // 保留this引用
      const resize = document.getElementById('resize2')
      resize.onmousedown = function (e) {
        document.getElementById('test').style.zIndex = 1
        // 颜色改变提醒
        resize.style.background = '#818181'
        let startX = e.clientX
        document.onmousemove = function (e) {
          // 计算并应用位移量
          const endX = e.clientX
          startX = endX
          document.getElementById('componentDetails-right').style.width = (document.body.clientWidth - startX) + 'px'
          document.getElementById('componentDetails-mid').style.width =
            (document.body.clientWidth - document.getElementById('componentDetails-left').clientWidth -
              document.getElementById('componentDetails-right').clientWidth - 10) + 'px'
        }
        document.onmouseup = function () {
          // 颜色恢复
          resize.style.background = ''
          document.onmousemove = null
          document.onmouseup = null
          document.getElementById('test').style.zIndex = -1
        }
        return false
      }
    }
  },
  components: {
    productDetails
  }
}
</script>
<style scoped lang="scss">
@import '~@/styles/common.scss';
.ipcFigureUrlList {
  display: flex;
  justify-content: left;
  align-items: center;
  margin-top: 3px;
  i {
    font-size: 20px;
  }
  &-name {
    color: #409eff;
    cursor: pointer;
    text-decoration: underline;
  }
}
.componentDetails {
  //overflow: hidden;
  height: 100%;
  display: flex;
  justify-content: space-between;
  &-left {
    width: 300px;
    height: 100%;
    //background-color: #20a0ff;
    flex-shrink: 0;
    overflow: auto;
  }
  &-mid {
    width: calc(100% - 760px);
    height: 100%;
    //background-color: lightcoral;
    flex-shrink: 0;
    overflow: auto;
  }
  &-right {
    width: 450px;
    height: 100%;
    flex-shrink: 0;
  }
  &-resize {
    height: 100%;
    width: 3px;
    background-color: #999999;
    cursor: w-resize;
    flex-shrink: 0;
  }
}
.componentDetails ::v-deep .productDetails .el-dialog__body {
  padding-top: 0;
}
.componentDetails ::v-deep .el-dialog__body {
  padding-top: 0px;
}
</style>

