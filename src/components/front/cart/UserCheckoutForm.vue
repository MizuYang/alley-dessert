<template>
      <Form action="/" v-slot="{ errors }" ref="form" @submit="sendOrder">
        <div class="row  mb-8 form_container ">
          <div class="col-12 col-lg-6 me-auto border p-4 p-md-5 mb-5">
            <h3 class="border-bottom text-center text-lg-start pb-2">訂購人資料</h3>
            <div class="mb-3">
              <label for="name"> 姓名 </label>
              <Field
                id="name"
                name="姓名"
                type="text"
                class="form-control bg-dark text-primary"
                :class="{ 'is-invalid': errors['姓名'] }"
                placeholder="請輸入姓名"
                rules="required"
                v-model="form.user.name"
              >
              </Field>
              <ErrorMessage name="姓名" class="invalid-feedback"></ErrorMessage>
            </div>
            <div class="mb-3">
              <label for="email"> E-mail </label>
              <Field
                type="email"
                id="email"
                placeholder="請輸入E-mail"
                class="form-control bg-dark text-primary"
                name="信箱"
                rules="email|required"
                :class="{ 'is-invalid': errors['信箱'] }"
                v-model="form.user.email"
              >
              </Field>
              <ErrorMessage name="信箱" class="invalid-feedback"></ErrorMessage>
            </div>
            <div class="mb-3">
              <label for="tel" class="form-label">收件人電話</label>
              <Field
                id="tel"
                name="電話"
                type="tel"
                class="form-control bg-dark text-primary"
                :class="{ 'is-invalid': errors['電話'] }"
                :rules="isPhone"
                placeholder="請輸入電話 / 例：09xxxxxxxx"
                maxlength="10"
                v-model="form.user.tel"
              ></Field>
              <ErrorMessage name="電話" class="invalid-feedback"></ErrorMessage>
            </div>
            <div class="mb-3">
              <label for="category"> 選擇付款方式 </label>
              <Field
              required
                id="category"
                name="付款方式"
                class="form-control form-select bg-dark text-primary"
                :class="{ 'is-invalid': errors['付款方式'] }"
                rules="required"
                as="select"
                v-model="form.user.pay_method"
              >
                <option value="" selected disabled>請選擇付款方式</option>
                <option value="現金 / 限自取">現金 / 限自取</option>
                <option value="信用卡付款">信用卡付款</option>
                <option value="超商付款">超商付款</option>
                <option value="LINE PAY">LINE PAY</option>
              </Field>
              <ErrorMessage
                name="付款方式"
                class="invalid-feedback"
              ></ErrorMessage>
            </div>
            <div class="mb-3">
              <label for="address"> 地址 </label>
              <Field
                type="address"
                id="address"
                placeholder="請輸入地址"
                class="form-control bg-dark text-primary"
                name="地址"
                rules="required"
                :class="{ 'is-invalid': errors['地址'] }"
                v-model="form.user.address"
              >
              </Field>
              <ErrorMessage name="地址" class="invalid-feedback"></ErrorMessage>
            </div>
          </div>
          <div class="col-12 col-lg-5 justify-content-center border p-4 p-md-5 mb-5">
            <h3 class="border-bottom text-center text-lg-start mb-4 pb-2">
              信用卡資料
            </h3>
            <div class="row">
              <div class="mb-1 d-flex justify-content-center">
                <Field
                  id=""
                  name="卡號"
                  type="text"
                  class="form-control bg-dark text-primary card-text mb-3"
                  :class="{ 'is-invalid': errors['卡號'] }"
                  placeholder="0000"
                  rules="required"
                  maxlength="4"
                  v-model="form.user.card1"
                >
                </Field>
                <ErrorMessage
                  name="卡號"
                  class="invalid-feedback"
                ></ErrorMessage>
                -
                <Field
                  id=""
                  name="卡號2"
                  type="text"
                  class="form-control bg-dark text-primary card-text"
                  :class="{ 'is-invalid': errors['卡號2'] }"
                  placeholder="0000"
                  rules="required"
                  maxlength="4"
                  v-model="form.user.card2"
                >
                </Field>
                <ErrorMessage
                  name="卡號2"
                  class="invalid-feedback"
                ></ErrorMessage>
                -
                <Field
                  id=""
                  name="卡號3"
                  type="text"
                  class="form-control bg-dark text-primary card-text"
                  :class="{ 'is-invalid': errors['卡號3'] }"
                  placeholder="0000"
                  rules="required"
                  maxlength="4"
                  v-model="form.user.card3"
                >
                </Field>
                <ErrorMessage
                  name="卡號3"
                  class="invalid-feedback"
                ></ErrorMessage>
                -
                <Field
                  id=""
                  name="卡號4"
                  type="text"
                  class="form-control bg-dark text-primary card-text"
                  :class="{ 'is-invalid': errors['卡號4'] }"
                  placeholder="0000"
                  rules="required"
                  maxlength="4"
                  v-model="form.user.card4"
                >
                </Field>
                <ErrorMessage
                  name="卡號4"
                  class="invalid-feedback"
                ></ErrorMessage>
                <div></div>
              </div>
              <div class="d-flex col-12 justify-content-center">
                <Field
                  id=""
                  name="卡號5"
                  type="text"
                  class="form-control bg-dark text-primary card-text card-text-rwd-width mb-2"
                  :class="{ 'is-invalid': errors['卡號5'] }"
                  placeholder="1/1"
                  rules="required"
                  maxlength="3"
                  v-model="form.user.card5"
                >
                </Field>
                <ErrorMessage
                  name="卡號5"
                  class="invalid-feedback"
                ></ErrorMessage>
                /
                <Field
                  id=""
                  name="卡號6"
                  type="text"
                  class="form-control bg-dark text-primary card-text card-text-rwd-width"
                  :class="{ 'is-invalid': errors['卡號6'] }"
                  placeholder="123"
                  rules="required"
                  maxlength="3"
                  v-model="form.user.card6"
                >
                </Field>
                <ErrorMessage
                  name="卡號6"
                  class="invalid-feedback"
                ></ErrorMessage>
                /
                <Field
                  id=""
                  name="持卡者名稱"
                  type="text"
                  class="form-control bg-dark text-primary card-user-name"
                  :class="{ 'is-invalid': errors['持卡者名稱'] }"
                  placeholder="英文名稱"
                  rules="required"
                  maxlength="3"
                  v-model="form.user.card_username"
                >
                </Field>
                <ErrorMessage
                  name="持卡者名稱"
                  class="invalid-feedback"
                ></ErrorMessage>
              </div>
            </div>
            <label for="textarea">留言</label> <br />
            <textarea name="留言" id="textarea" class="textarea bg-dark text-primary mx-auto"
            cols="60" rows="8" v-model="form.message"></textarea>
          </div>
          <UserCheckoutOrder />
        </div>
      </Form>
</template>

<script>
import UserCheckoutOrder from '@/components/front/cart/UserCheckoutOrder.vue'
export default {
  inject: ['emitter'],

  components: {
    UserCheckoutOrder
  },

  data () {
    return {
      cartData: [],
      form: {
        user: {
          name: '王先生',
          email: '123456@gmail.com',
          tel: '0999999123',
          address: '台北',
          pay_method: '超商付款',
          card1: '123',
          card2: '312',
          card3: '312',
          card4: '312',
          card5: '312',
          card6: '312',
          card_username: '王先生'
        },
        message: '你好'
      }
    }
  },

  methods: {
    sendOrder () {
      const api = `${process.env.VUE_APP_API}/api/${process.env.VUE_APP_PATH}/order`
      this.$http.post(api, { data: this.form }).then((res) => {
        const orderId = res.data.orderId
        this.$router.push(`/order_confirm/${orderId}`)
      }).catch(() => {
        this.$httpMessageState(false, '購物車為空，發送訂單')
        this.$router.push('/products')
      })
    },
    isPhone (value) {
      const phoneNumber = /^(09)[0-9]{8}$/
      return phoneNumber.test(value) ? true : '*請輸入 09 開頭的正確電話號碼'
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/stylesheets/helpers/_rwdMixin.scss";
@import "@/assets/stylesheets/helpers/front/cart/_UserCheckoutForm.scss";
</style>
