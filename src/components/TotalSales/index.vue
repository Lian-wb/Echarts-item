<template>
  <div class="total-sales">
    <common-card title="累计销售额" :value="salesToday">
      <template>
        <div class="compare-wrapper">
          <div class="compare">
            <span>日同比</span>
            <span class="emphasis">{{ salesGrowthLastDay }}</span>
            <div class="increase"></div>
          </div>
          <div class="compare">
            <span>月同比</span>
            <span class="emphasis">{{ salesGrowthLastMonth }}</span>
            <div class="decrease"></div>
          </div>
        </div>
      </template>

      <!-- 传给footer插槽 -->
      <template v-slot:footer>
        <span>昨日销售额 </span>
        <span class="emphasis">{{ salesLastDay }}</span>
        <!-- <div>getReportData:{{ reportData }}</div> -->
      </template>
    </common-card> 
  </div>
</template>

<script>
import commonCardMixin from "../../mixin/commonCardMixin";
import commonDataMixin from "../../mixin/commonDataMixin";
export default {
  name: "TotalSales",
  mixins: [commonCardMixin, commonDataMixin],
};
</script>

<style lang="scss" scoped>
.compare-wrapper {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  .compare {
    display: flex;
    align-items: center;
    font-size: 12px;
    // background: rgb(239, 157, 157);
    margin-top: 3px;
    color: #666;
  }
}
</style>
