<template>
  <div>
    <div class="wrapper">
      <div class="toolbar">
        <div class="toolbar_line">
          <div class="container">
            <div class="toolbar_line__support">
              <span>Служба техподдержки:</span> 8 800 500-40-20
            </div>
            <div class="toolbar_line__right">
              <div class="line_right__valute">
                <div class="dropdown">
                  <button
                    class="line_right__valute___dropdown"
                    type="button"
                    id="dropdownMenuButton"
                    data-toggle="dropdown"
                    aria-haspopup="true"
                    aria-expanded="false"
                  >
                    <div class="valute">
                      <span></span> 1,500
                      <small>₽</small>
                    </div>
                    <span>Вывести</span>
                  </button>
                  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                    <a class="dropdown-item" href="#">
                      14,500
                      <small>₽</small>
                    </a>
                    <a class="dropdown-item" href="#">
                      700
                      <small>$</small>
                    </a>
                    <a class="dropdown-item" href="#">
                      450
                      <small>€</small>
                    </a>
                    <div class="dropdown-divider"></div>
                    <a class="dropdown-item" href="#">
                      550
                      <small>LB</small>
                    </a>
                  </div>
                </div>
              </div>

              <div class="line_right__profile">
                <div class="dropdown">
                  <button
                    class="dropdown-toggle line_right__profile___dropdown"
                    type="button"
                    id="dropdownMenuButton"
                    data-toggle="dropdown"
                    aria-haspopup="true"
                    aria-expanded="false"
                  >
                    <img class="profile_avatar" src="./img/ava_30x30x2.png">
                    <div class="profile_name">Артем</div>
                  </button>
                  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                    <a class="dropdown-item" href="#">Профиль</a>
                    <a class="dropdown-item" href="#">Настройки</a>
                    <a class="dropdown-item" href="#">Выход</a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="toolbar_menu">
          <div class="container">
            <a href="index.html" class="toolbar_menu__logo">
              <img src="./img/logo.svg">
            </a>
            <div class="toolbar_menu__right">
              <a href="index.html" class="act">Заведения</a>
              <a href="cashback.html">Кэшбэк</a>
            </div>

            <div class="toolbar_menu__dropdown">
              <div class="dropdown">
                <button
                  class="toolbar_menu__dropdown___button"
                  type="button"
                  id="dropdownMenuButton"
                  data-toggle="dropdown"
                  aria-haspopup="true"
                  aria-expanded="false"
                >
                  <i class="fas fa-bars"></i>
                </button>
                <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                  <a class="dropdown-item act" href="index.html">Заведения</a>
                  <a class="dropdown-item" href="cashback.html">Кэшбэк</a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="inner">
        <div class="container">
          <div class="side">
            <div class="side_card">
              <div class="side_card__title">Информация о карте</div>
              <div class="side_card__name">Артем Райм</div>
              <div class="side_card__number">
                <img src="./img/side_car.svg"> 000 000 432
              </div>
            </div>
            <div class="slide_cat">
              <div class="slide_cat__title">Категории</div>
              <div class="slide_cat__box">
                <label class="main_checkbox">
                  <input type="checkbox" checked="checked">
                  <span class="checkmark"></span>
                  Все
                </label>
                <label class="main_checkbox">
                  <input type="checkbox">
                  <span class="checkmark"></span>
                  Магазины
                </label>
                <label class="main_checkbox">
                  <input type="checkbox">
                  <span class="checkmark"></span>
                  Еда
                </label>
                <label class="main_checkbox">
                  <input type="checkbox">
                  <span class="checkmark"></span>
                  Авто
                </label>
                <label class="main_checkbox">
                  <input type="checkbox">
                  <span class="checkmark"></span>
                  Сфера услуг
                </label>
              </div>
            </div>
          </div>
          <div class="content">
            <div class="bunner">
              <a href="#">
                <img src="./img/bunner.png">
              </a>
            </div>
            <div class="content_bar">
              <div class="content_bar__title">
                <h2>Заведения</h2>
                <nav aria-label="breadcrumb">
                  <ol class="breadcrumb">
                    <li class="breadcrumb-item">
                      <a href="#">Home</a>
                    </li>
                    <li class="breadcrumb-item active" aria-current="page">Library</li>
                  </ol>
                </nav>
              </div>
              <div class="content_bar__sorting">
                Сортировка:
                <div class="content_bar__sorting__items">
                  <h3 @click="favorite()">Избранное</h3>
                  <h3 @click="newShops()">Новое</h3>
                </div>

                <!--<select>
                  <option @click="favorite()">Избраные</option>
                  <option>Новое</option>
                </select>-->
              </div>
            </div>
            <div class="shop">
              <div class="container_fluid">
                <div class="row">
                  <div class="col-xl-4" v-for="(shop, i) in shops" :key="`${i}-${shop}`">
                    <a href class="shop_item">
                      <div class="shop_item__title">
                        <h3>{{shop.title}}</h3>
                        <div class="shop_item__title___right">
                          <button class="like" @click="like(i)">
                            <i class="fas fa-heart"></i>
                          </button>
                        </div>
                      </div>
                      <div class="shop_item__center">
                        <div class="shop_item__center___avatar">
                          <div class="shop_avatar">
                            <!--<img src="./img/shop_avatar_70x70x2.png">-->
                            <img v-bind:src="shop.img">
                            <span>4,3</span>
                          </div>
                        </div>
                        <div class="shop_item__center___text">
                          <p>{{shop.subtitle}}</p>
                        </div>
                      </div>
                      <div class="shop_item__bonus">
                        <h3>
                          5 - 10
                          <small>%</small>
                        </h3>
                        <span>Бонусов</span>
                      </div>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "app",
  components: {},
  data() {
    return {
      shops: [],
      shop: {},
      data: [],
      title: "",
      img: "",
      subtitle: ""
    };
  },
  methods: {
    like: async function(i) {
      await axios({
        method: "post",
        url: "http://localhost:3000/favoriteshops",
        data: {
          title: this.shops[i].title,
          img: this.shops[i].img,
          subtitle: this.shops[i].subtitle,
          like: true
        }
      });
    },
    favorite: async function() {
      await axios
        .get("http://localhost:3000/favoriteshops")
        .then(response => (this.shops = response.data));
    },
    newShops: async function() {
      await axios
        .get("http://localhost:3000/listshops")
        .then(response => (this.shops = response.data));
    }
  },
  mounted: async function() {
    await axios
      .get("http://localhost:3000/listshops")
      .then(response => (this.shops = response.data));
  }
};
</script>

<style>
@import "assets/css/style.css";
</style>
