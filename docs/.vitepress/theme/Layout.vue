<template>
  <ParentLayout>
    <template #navbar-search>
      <AlgoliaSearchBox :options="$site.themeConfig.algolia" />
    </template>
    <template #page-top>
      <CarbonAds
        v-if="$site.themeConfig.carbonAds"
        :key="'carbon' + $page.path"
        :code="$site.themeConfig.carbonAds.carbon"
        :placement="$site.themeConfig.carbonAds.placement"
      />
    </template>
    <template #page-bottom>
    <div id="ad">
      <a href="javascript:viod(0)" target="_blank" rel="sponsored noopener">
        关注Vue中文社区回复1入500人前端群
        <img src="http://static.vue-js.com/FoACtDzI5t3Bm4VIrZA3cVm1y7o4"></a> 
        <!-- <a href="javascript:viod(0)" target="_blank" rel="sponsored noopener">
        拉你进500人前端群
        <img src="http://static.vue-js.com/Fr6pvXKNio5Pe4kEHk0ufXdZ1sHT"></a> -->
    </div>
    </template>

  </ParentLayout>
</template>

<script>
import DefaultTheme from 'vitepress/dist/client/theme-default'
import CarbonAds from './components/CarbonAds.vue'
import BuySellAds from './components/BuySellAds.vue'
import AlgoliaSearchBox from './components/AlgoliaSearchBox.vue'

export default {
  name: 'Layout',

  components: {
    ParentLayout: DefaultTheme.Layout,
    CarbonAds,
    BuySellAds,
    AlgoliaSearchBox,
  },
}
</script>

<style lang="styl">
form {
  margin-block-end: 0;
}

.custom-blocks {
  overflow-x: auto;
}

#ad
    width: 135px;
    position: fixed;
    z-index: $z-header -1;
    right: 10px;
    top: 120px;
    padding: 10px;
    background-color: #fff;
    border-radius: 3px;
    font-size: 13px;
    text-align: center;
  /* img */
    

#ad  .img{
  width:  100%;
}

@media (max-width: 500px)
  #ad
    display: none

</style>
