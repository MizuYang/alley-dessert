<template>
  <div
    class="modal fade"
    id="couponModal"
    tabindex="-1"
    role="dialog"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
    ref="modal"
  >
    <div class="modal-dialog modal-dialog-centered" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title text-dark" id="exampleModalLabel">
            <span v-if="isNew">新增優惠卷</span>
            <span v-else>編輯優惠卷</span>
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body text-dark">
          <div class="mb-3">
            <label for="title">標題</label>
            <input
              type="text"
              class="form-control"
              id="title"
              v-model="tempCoupon.title"
              placeholder="請輸入標題"
            />
          </div>
          <div class="mb-3">
            <label for="coupon_code">優惠碼</label>
            <input
              type="text"
              class="form-control"
              id="coupon_code"
              v-model="tempCoupon.code"
              placeholder="請輸入優惠碼"
            />
          </div>
          <div class="mb-3">
            <label for="due_date">到期日</label>
            <input
              type="date"
              class="form-control"
              id="due_date"
              v-model="due_date"
            />
          </div>
          <div class="mb-3">
            <label for="price">折扣百分比</label>
            <input
              type="number"
              class="form-control"
              id="price"
              min="0%"
              max="100%"
              v-model.number="tempCoupon.percent"
              placeholder="請輸入折扣百分比"
            />
            <i class="text-danger" v-if="!couponDiscountRule">請輸入 0~100 折扣碼!!</i>
          </div>
          <div class="mb-3">
            <div class="form-check">
              <label class="form-check-label" for="is_enabled">
                是否啟用
              </label>
              <input
                class="form-check-input"
                type="checkbox"
                :true-value="1"
                :false-value="0"
                v-model="tempCoupon.is_enabled"
                id="is_enabled"
              />
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            data-bs-dismiss="modal"
          >
            關閉
          </button>
          <button
            type="button"
            class="btn btn-primary"
            @click="updateCoupon(tempCoupon.id)"
          >
            {{ isNew ? "新增優惠卷" : "更新優惠券" }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Modal from 'bootstrap/js/dist/modal'
export default {
  inject: ['emitter'],

  data () {
    return {
      couponModal: '',
      isNew: false,
      tempCoupon: {},
      due_date: '',
      couponDiscountRule: true
    }
  },

  methods: {
    updateCoupon (id) {
      this.couponDiscountRule = this.tempCoupon.percent <= 100 && this.tempCoupon.percent > 0
      if (!this.couponDiscountRule) {
        this.tempCoupon.percent = 0
        this.$httpMessageState(false, '請輸入正確的數字，更新優惠券')
        return
      }
      let methods = 'post'
      let api = `${process.env.VUE_APP_API}/api/${process.env.VUE_APP_PATH}/admin/coupon`
      if (this.isNew) {
        this.tempCoupon.due_date = Math.floor(new Date(this.due_date) / 1000)
      } else if (!this.isNew) {
        methods = 'put'
        api = `${process.env.VUE_APP_API}/api/${process.env.VUE_APP_PATH}/admin/coupon/${id}`
        this.tempCoupon.due_date = Math.floor(new Date(this.due_date) / 1000)
      }
      this.$http[methods](api, { data: this.tempCoupon })
        .then((res) => {
          this.$httpMessageState(res.data.success, '更新優惠券')
          this.couponModal.hide()
          this.$emit('getCoupon')
          this.tempCoupon = {}
        })
        .catch((err) => this.$httpMessageState(err.success, '更新優惠券'))
    }
  },

  mounted () {
    this.couponModal = new Modal(document.getElementById('couponModal'))
    this.emitter.on('openCouponModal', (item) => {
      this.couponModal.show()
      this.tempCoupon = {}
      this.due_date = ''
      this.isNew = true
      if (item) {
        this.isNew = false
        //* 先將優惠券日期外的欄位賦予上值
        this.tempCoupon = item
        //* 將時間戳轉為日期格式
        const dateAndTime = new Date(item.due_date * 1000)
          .toISOString()
          .split('T')
        //* 再將日期賦予上去 (日期的 v-model 是分開寫的)
        this.due_date = dateAndTime[0]
      }
      setTimeout(() => this.couponModal.show(), 1000)
    })
  },

  unmounted () {
    this.emitter.off('openCouponModal')
  }
}
</script>
