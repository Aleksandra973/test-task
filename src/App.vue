<template>
  <main>
    <h1>Входное тестовое</h1>
    <p>
      Входное тестовое нужно, чтобы мы понимали твой уровень JavaScript и Vue,
      умение работать с REST API.
    </p>
    <p>
      На проекте подключен Bootstrap, чтобы сэкономить ваше время на вёрстку.
    </p>
    <ul>
      <li>
        API документация:
        <a target="_blank" href="https://vue-study.dev.creonit.ru/"
          >https://vue-study.dev.creonit.ru/</a
        >
      </li>
      <li>
        Bootstrap:
        <a
          href="https://getbootstrap.com/docs/4.5/getting-started/introduction/"
          >https://getbootstrap.com/docs/4.5/getting-started/introduction/</a
        >
      </li>
      <li>
        Vue документация:
        <a href="https://vuejs.org/v2/guide/">https://vuejs.org/v2/guide/</a>
        <br />
        Вам понадобиться v-model, v-for, v-bind, computed свойства и рендер
        хуки.
      </li>
    </ul>

    <p>Что будет учитываться при оценке:</p>
    <ol>
      <li>Чистота кода.</li>
      <li>Компонентный подход.</li>
      <li>
        Внимательность. Где-то в постановке и текущей реализации могут быть
        допущены ошибки :-)
      </li>
      <li>Использование фич Vue.</li>
      <li>Использование ES6.</li>
    </ol>

    <div class="alert alert-secondary" role="alert">
      Вы получили вёрстку, которую надо интегрировать с бэком.
      <hr />
      Результат должен быть на платформе `codesandbox`.
      <br />
      Можете разрабатывать локально, но сюда потом перенести придётся. На других
      платформах задание проверяться не будет.
    </div>

    <section class="container mb-5">
      <h2>Первое задание</h2>
      <p>Нужно отправить форму Оформления заказа на сервер.</p>
      <p>
        /api/orders:
        <a
          target="_blank"
          href="https://vue-study.dev.creonit.ru/#/Orders/post_api_orders"
          >https://vue-study.dev.creonit.ru/#/Orders/post_api_orders</a
        >
      </p>
      <h3>Требования:</h3>
      <ol>
        <li>
          Сбор данных в форме должен быть реализован на Vue. На всякий случай
          уточняю :-)
        </li>
        <li>
          Обработка ошибок по полям. Ошибки будут приходить в ответе, если вдруг
          поля невалидные.
        </li>
      </ol>
      <h3>Уточнения</h3>
      <ol>
        <li>
          Чтобы полностью отправить форму, нужно перед этим запросить
          пользовательский ключ `/api/users/accessKey`.
        </li>
        <li>
          Форма до конца не отправиться с новым ключом, потому что тогда корзина
          будет пустая. Если вы дошли до этого — считайте что задание готово ;-)
        </li>
      </ol>
      <h4>Оценка менеджера</h4>
      <p>~20 минут. Если незнакомы с Vue — 40 минут.</p>

      <form>
        <div class="form-group">
          <label class="d-block">
            <div class="mb-2">Представьтесь</div>
            <input
              type="text"
              v-model="form.name"
              :class="[{ 'is-invalid': error.name }, 'form-control']"
            />
            <div v-if="error.name" class="invalid-feedback">
              {{ error.name }}
            </div>
          </label>
        </div>
        <div class="form-group">
          <label class="d-block">
            <div class="mb-2">Адрес доставки</div>
            <input
              type="text"
              v-model="form.address"
              :class="[{ 'is-invalid': error.address }, 'form-control']"
            />
            <div v-if="error.address" class="invalid-feedback">
              {{ error.address }}
            </div>
          </label>
        </div>
        <div class="form-group">
          <label class="d-block">
            <div class="mb-2">Телефон</div>
            <input
              type="tel"
              v-model="form.phone"
              :class="[{ 'is-invalid': error.phone }, 'form-control']"
            />
            <div v-if="error.phone" class="invalid-feedback">
              {{ error.phone }}
            </div>
          </label>
        </div>
        <div class="form-group">
          <label class="d-block">
            <div class="mb-2">Эл. почта</div>
            <input
              type="email"
              v-model="form.email"
              :class="[{ 'is-invalid': error.email }, 'form-control']"
            />
            <div v-if="error.email" class="invalid-feedback">
              {{ error.email }}
            </div>
          </label>
        </div>
        <div class="form-group">
          <label class="d-block">
            <div class="mb-2">Комментарий</div>
            <textarea v-model="form.comment" class="form-control"></textarea>
          </label>
        </div>
        <button @click="submit" type="button" class="btn btn-primary">
          Отправить
        </button>
      </form>
    </section>

    <section class="container mb-5">
      <h2>Второе задание</h2>
      <p>
        Нужно доделать вывод товаров. Кто-то начал задачу, а вас попросили
        закончить начатое.
      </p>
      <p>Вывести товары нужно из категории с `id: 3`</p>
      <p>
        /api/products:
        <a
          target="_blank"
          href="https://vue-study.dev.creonit.ru/#/Products/get_api_products"
          >https://vue-study.dev.creonit.ru/#/Products/get_api_products</a
        >
      </p>
      <h3>Требования:</h3>
      <ol>
        <li>
          Товары должны выводиться из вычесляемого свойства `productsItems`.
        </li>
        <li>
          Формат данных продукта возвращаемого `productsItems` должен
          соответствовать типу `Product`.
        </li>
      </ol>
      <h4>Оценка менеджера</h4>
      <p>~10 минут. Если незнакомы с Vue — 20 минут.</p>
      <div class="row">
        <div v-for="item in productsItems" :key="item.id" class="col-4">
          <div class="card">
            <img
                :src="item.image"
                class="card-img-top card-exp"
                alt="Название"
            />
            <div class="card-body">
              <h5 class="card-title">{{item.title}}</h5>
              <a href="#" class="card-link" :style="`color: ${color.code}`" v-for="color in item.colors" :key="color.id">{{color.title}}</a>
            </div>
          </div>
        </div>
      </div>
      <h4>Дополнительное задание</h4>
      <p>
        Зарефакторить карточку товара используя БЭМ наименование. Это ещё займёт
        10 минут.
      </p>
      <div class="row">
        <div class="col-6">
          <div class="card-item">
            <img
              src="http://placehold.it/200x200"
              class="card-item__img"
              alt="Название"
            />
            <div class="card-item__body">
              <h5 class="card-item__title">Детский трюковой самокат Razor Grom</h5>
              <h6 class="card-item__subtitle card-item__subtitle_muted">4 990 ₽</h6>
              <a href="#" class="card-item__link card-item__link_color_blue">Синий</a>
              <a href="#" class="card-item__link card-item__link_color_green">Зелёный</a>
            </div>
          </div>
        </div>
        <div class="col-6">
          <div class="card-item">
            <img
              src="http://placehold.it/200x200"
              class="card-item__img"
              alt="Название"
            />
            <div class="card-item__body">
              <h5 class="card-item__title">Детский самокат Razor</h5>
              <h6 class="card-item__subtitle card-item__subtitle_muted">5 990 ₽</h6>
              <a href="#" class="card-item__link card-item__link_color_blue">Синий</a>
            </div>
          </div>
      </div>
      </div>
    </section>
  </main>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";

import axios from "axios";

/**
 * Метод для получение товаров из категории
 * @todo Реализовать получение товаров
 * @param {string | number} category id/slug категории
 */
axios
  .get("https://vue-study.dev.creonit.ru/api/products", {
    params: {
      categoryId: 3,
    },
  })
  .then((response) => {
    console.log(response);
  });

/**
 * Объект продукта
 * @typedef Product
 * @property {number} id айди
 * @property {string} title заголовок
 * @property {string} [image] ссылка на картинку
 * @property {Array <Object>} [colors] возможные цвета
 */

export default {
  name: "App",
  data() {
    return {
      form: {
        name: "",
        address: "",
        phone: "",
        email: "",
        comment: "",
      },
      products: null,
      error: {
        name: "",
        address: "",
        phone: "",
        email: "",
      },
    };
  },
  methods: {
    async submit() {
      let key = await axios.get(
        "https://vue-study.dev.creonit.ru/api/users/accessKey"
      );
      axios({
        method: "post",
        url: "https://vue-study.dev.creonit.ru/api/orders",
        data: this.form,
        params: {
          accessKey: key.data.accessKey,
        },
      })
          .then()
          .catch((e)=> {
            let errors = e.response.data.error
            this.error.name = errors.request.name;
            this.error.address = errors.request.address;
            this.error.email = errors.request.email;
            this.error.phone = errors.request.phone;
          });
    },
    getProducts() {
      axios
          .get("https://vue-study.dev.creonit.ru/api/products", {
            params: {
              categoryId: 3,
            },
          })
          .then((response) => {
            console.log(response.data.items)
            this.products = response.data.items.map (item => {
              return {
                  id: item.id,
                  title: item.title,
                  image:item.image.file.url,
                  colors: item.colors

            }})
          });
    }
  },
  mounted() {
    this.getProducts()
  },
  components: {},
  computed: {
    /**
     * @returns {Array <Product> | null}
     */
    productsItems() {
      return this.products;
    },
  },
};
</script>

<style lang="scss">
@import "../node_modules/bootstrap";

.card{
  align-items: center !important
}
.card-exp{
  object-fit: contain;
  max-height: 200px;
  max-width: 200px;
}

.card-item{
  @extend .card;
  &_size_6{
    @extend .col-6;
  }
  &__img{
   @extend .card-img-top
  }
  &__body {
    @extend .card-body
  }
  &__title{
    @extend .card-title
  }
  &__subtitle{
    @extend .card-subtitle;
    @extend .mb-2;
    &_muted{
      @extend .text-muted
    };
  }
  &__link{
    @extend .card-link;
    &_color_green{
      color: green;
    };
    &_color_blue{
      color: blue;
    };
  }
}



</style>