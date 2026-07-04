<script setup>
import { reactive, ref } from "vue";

const reservation = reactive({
  date: "",
  time: "",
  guests: "",
  phone: "",
});

const bookingMessage = ref("");

function submitReservation() {
  bookingMessage.value = "已收到预约信息，我们会尽快与您确认。";
  reservation.date = "";
  reservation.time = "";
  reservation.guests = "";
  reservation.phone = "";
}
</script>

<template>
  <header class="hero" id="top">
    <nav class="nav" aria-label="主导航">
      <a class="brand" href="#top">岚庭</a>
      <div class="nav-links">
        <a href="#menu">菜单</a>
        <a href="#experience">体验</a>
        <a href="#visit">到店</a>
        <a class="reserve-link" href="#reserve">预约</a>
      </div>
    </nav>

    <div class="hero-content">
      <p class="eyebrow">Seasonal Dining · Shanghai</p>
      <h1>把一顿晚餐，做成值得停留的夜晚。</h1>
      <p class="hero-copy">
        岚庭以当季食材、明火烹调与轻松的餐酒节奏，呈现适合约会、好友聚餐和小型庆祝的城市餐桌。
      </p>
      <div class="hero-actions">
        <a class="button button-primary" href="#reserve">立即预约</a>
        <a class="button button-secondary" href="#menu">查看招牌菜</a>
      </div>
    </div>
  </header>

  <aside class="hero-panel" aria-label="餐馆概览">
    <div class="panel-item">
      <span class="panel-label">Tonight</span>
      <span class="panel-value">17:30 开始供应晚餐</span>
    </div>
    <div class="panel-item">
      <span class="panel-label">Signature</span>
      <span class="panel-value">炭烤、时蔬、自然酒</span>
    </div>
    <div class="panel-item">
      <span class="panel-label">Location</span>
      <span class="panel-value">安静街角，近地铁 2 号线</span>
    </div>
  </aside>

  <main>
    <section class="section" id="menu">
      <div class="section-inner">
        <div class="intro">
          <div>
            <p class="section-kicker">Menu Highlights</p>
            <h2>每天按市场状态调整的晚餐菜单。</h2>
          </div>
          <p class="lead">
            厨房保留食材本来的鲜度，用炭火、发酵、香草和手工酱汁建立层次。菜单不追求复杂词汇，只追求入口后清楚、舒服、想再吃一口。
          </p>
        </div>

        <div class="signature-grid">
          <article class="dish-card">
            <div class="dish-top">
              <h3>炭烤牛肋眼</h3>
              <span class="price">¥188</span>
            </div>
            <p>配黑蒜汁、烤小胡萝卜与迷迭香海盐，火候外焦内嫩。</p>
          </article>
          <article class="dish-card">
            <div class="dish-top">
              <h3>香草青酱海鲈鱼</h3>
              <span class="price">¥138</span>
            </div>
            <p>低温慢烤后以柠檬皮提亮，搭配脆口时蔬与橄榄油。</p>
          </article>
          <article class="dish-card">
            <div class="dish-top">
              <h3>焦糖无花果布丁</h3>
              <span class="price">¥58</span>
            </div>
            <p>温热布丁、烤坚果与淡奶油，收尾柔和但有记忆点。</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section experience" id="experience">
      <div class="section-inner experience-layout">
        <div>
          <p class="section-kicker">Dining Experience</p>
          <h2>不紧绷的精致感，才适合真正放松地吃饭。</h2>
          <p class="lead">
            从开胃小食到餐后甜点，服务节奏会跟着你的桌边气氛走。你可以让我们配酒，也可以只点一杯好喝的餐前酒慢慢开始。
          </p>
          <ul class="feature-list">
            <li>
              <strong>开放式厨房</strong>
              <span>看得到火候，也闻得到刚出炉的香气。</span>
            </li>
            <li>
              <strong>小产区酒单</strong>
              <span>自然酒、起泡酒和低酒精选择都有。</span>
            </li>
            <li>
              <strong>8 人包间</strong>
              <span>适合生日、项目庆功和安静家宴。</span>
            </li>
          </ul>
        </div>

        <form class="booking" id="reserve" @submit.prevent="submitReservation">
          <h3>预留今晚的位置</h3>
          <p>提交后我们会在营业时间内确认桌位和特殊需求。</p>
          <div class="booking-row">
            <div class="booking-field">
              <label for="reservation-date">日期</label>
              <input
                id="reservation-date"
                v-model="reservation.date"
                name="date"
                type="date"
                required
              />
            </div>
            <div class="booking-field">
              <label for="reservation-time">时间</label>
              <select
                id="reservation-time"
                v-model="reservation.time"
                name="time"
                required
              >
                <option value="">请选择</option>
                <option>17:30</option>
                <option>18:00</option>
                <option>18:30</option>
                <option>19:00</option>
                <option>19:30</option>
                <option>20:00</option>
                <option>20:30</option>
                <option>21:00</option>
              </select>
            </div>
            <div class="booking-field">
              <label for="reservation-guests">人数</label>
              <select
                id="reservation-guests"
                v-model="reservation.guests"
                name="guests"
                required
              >
                <option value="">请选择</option>
                <option>1 人</option>
                <option>2 人</option>
                <option>3 人</option>
                <option>4 人</option>
                <option>5 人</option>
                <option>6 人</option>
                <option>7 人</option>
                <option>8 人</option>
              </select>
            </div>
            <div class="booking-field">
              <label for="reservation-phone">手机号</label>
              <input
                id="reservation-phone"
                v-model="reservation.phone"
                name="phone"
                type="tel"
                inputmode="tel"
                autocomplete="tel"
                placeholder="请输入手机号"
                pattern="^1[3-9][0-9]{9}$"
                required
              />
            </div>
          </div>
          <button class="button" type="submit">提交预约</button>
          <p class="booking-message" id="booking-message" aria-live="polite">
            {{ bookingMessage }}
          </p>
        </form>
      </div>
    </section>

    <section class="section" id="visit">
      <div class="section-inner visit-grid">
        <div>
          <p class="section-kicker">Visit Us</p>
          <h2>来之前不用赶，留一点时间给晚风。</h2>
          <div class="hours" aria-label="营业时间">
            <div>
              <strong>周二至周五</strong>
              <span>17:30 - 22:30</span>
            </div>
            <div>
              <strong>周六至周日</strong>
              <span>11:30 - 14:30 / 17:30 - 23:00</span>
            </div>
            <div>
              <strong>周一</strong>
              <span>店休</span>
            </div>
          </div>
        </div>
        <div class="map-card">
          <p>上海市静安区梧桐路 18 号一层</p>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="footer-inner">
      <strong>岚庭餐馆</strong>
      <span>订位电话：021-5566-0888 · hello@lanting.example</span>
    </div>
  </footer>
</template>
