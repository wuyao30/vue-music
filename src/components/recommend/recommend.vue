<template>
  <div>
    recommend
  </div>
</template>

<script>
import { ERR_OK } from '../../api/config'
import { getRecommend } from '../../api/recommend'

export default {
  name: 'Recommend',
  data() {
    return {
      recommends: []
    }
  },
  created() {
    this._getRecommend()
  },
  methods: {
    _getRecommend() {
      getRecommend().then(res => {
        if (res.code === ERR_OK) {
          this.recommends = res.data.slider
          console.log(this.recommends)
        }
      })
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
