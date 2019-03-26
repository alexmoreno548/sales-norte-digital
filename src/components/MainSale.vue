<template>
  <section class="main_sale">
    <div class="container main_sale__container">
      <div class="row main_sale__wrapper">
        <div class="col-1">
          <img class="main_sale__img" src="@/assets/images/girl-box.svg" alt>
        </div>
        <div class="col-11">
          <h2 class="main_sale__title main_sale--texts">New Sale</h2>
          <hr>
        </div>
      </div>
      <div class="row main_sale__content--padd">
        <div class="col-12">
          <h3 class="main_sale--texts">Document</h3>
        </div>
      </div>
      <div class="row main_sale__form main_sale__input-btn">
        <div class="col-4 main_sale--texts">
          <p>Client</p>
          <model-select
            :options="clients"
            v-model="sale.client"
            placeholder="select item"
            ref="client"
            id="clients"
          ></model-select>
        </div>
        <div class="col-1 main_sale__wrapper-btn-close">
          <button class="btn-primary main_sale__btn-close" @click="addClient()">+</button>
        </div>
        <div class="col-5 main_sale--texts">
          <p>Branch office</p>
          <model-select
            :options="branches"
            v-model="branch"
            placeholder="select item"
            @input="setBranch"
            ref="branch"
            id="branches"
          ></model-select>
        </div>
        <div class="col-2 main_sale--texts">
          <p>Currency</p>
          <input type="text" class="form-control main_sale__input" :value="sale.currency">
        </div>
      </div>
      <div class="row main_sale__content--padd">
        <div class="col-12">
          <h3 class="main_sale--texts">Details</h3>
        </div>
      </div>
      <template>
        <div class="row main_sale__form" v-for="(product, index) in sale.products" :key="index">
          <div class="col-5 main_sale--texts">
            <p>Name</p>
            <model-select
              :options="products"
              v-model="product.price"
              placeholder="select item"
              @input="onSelect(index, product)"
            ></model-select>
          </div>
          <div class="col-2 main_sale--texts">
            <p>Quantity</p>
            <input
              type="text"
              class="form-control main_sale__input"
              v-model.number="product.quantity"
              @keyup="calcSubTotal(index)"
            >
          </div>
          <div class="col-2 main_sale--texts">
            <p>Price</p>
            <input
              type="text"
              class="form-control main_sale__input"
              v-model.number="product.price"
              readonly
            >
          </div>
          <div class="col-2 main_sale--texts">
            <p>Subtotal</p>
            <input
              type="text"
              class="form-control main_sale__input"
              v-model="product.subtotal"
              readonly
            >
          </div>
          <div class="col-1 main_sale--texts main_sale__wrapper-btn-close">
            <button class="btn-primary main_sale__btn-close" @click="deleteProduct(index)">x</button>
          </div>
        </div>
      </template>
      <div class="row">
        <div class="col-12 main_sale__wrapper-btn-add">
          <button class="btn-primary main_sale__btn-add" @click="addProduct">Add</button>
        </div>
      </div>
      <div class="row">
        <div class="col-2 offset-9 d-flex">
          <p class="mr-2">Total</p>
          <input
            type="text"
            class="form-control main_sale__input"
            :value="total"
            ref="total"
            readonly
          >
        </div>
      </div>
      <div class="row">
        <div class="col-2 offset-10">
          <button class="btn-primary main_sale__btn-save" @click="save">Save</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import { ModelSelect } from "vue-search-select";

export default {
  name: "MainSale",
  components: {
    ModelSelect
  },
  data() {
    return {
      sale: {
        client: "",
        branchOffice: "",
        currency: "",
        total: 0,
        products: [
          {
            name: "",
            quantity: 1,
            price: 0,
            subtotal: 0
          }
        ]
      },
      clients: [],
      branches: [],
      branch: "",
      products: []
    };
  },
  mounted() {
    axios.get("https://jsonplaceholder.typicode.com/users").then(
      response =>
        (this.clients = response.data.map(function(result) {
          return {
            value: result.name,
            text: result.name
          };
        }))
    );
    axios.get("https://restcountries.eu/rest/v2/region/americas").then(
      response =>
        (this.branches = response.data.map(function(result) {
          return {
            value: result.alpha2Code,
            text: result.name,
            branch: result
          };
        }))
    );
    axios.get("http://fakerestapi.azurewebsites.net/api/books").then(
      response =>
        (this.products = response.data.map(function(result) {
          return {
            value: result.PageCount,
            text: result.Title,
            price: result.PageCount
          };
        }))
    );
  },
  methods: {
    addProduct() {
      this.sale.products.push({
        name: "",
        quantity: 1,
        price: 0,
        subtotal: 0
      });
    },
    deleteProduct(index) {
      this.sale.products.splice(index, 1);
    },
    setBranch() {
      let aux = this.branches.find(value => {
        return value.value == this.branch;
      });
      this.sale.currency = aux.branch.currencies[0].code;
      this.sale.branchOffice = aux.branch.name;
    },
    calcSubTotal(index) {
      this.sale.products[index].subtotal =
        this.sale.products[index].quantity * this.sale.products[index].price;
    },
    onSelect(index, product) {
      this.calcSubTotal(index);
      product.name = "HOLA";
    },
    addClient() {
      let newClient = prompt("Ingrese nuevo cliente", "Nombre cliente:");
      this.clients.push({ text: newClient, value: newClient });
      this.sale.client = newClient;
    },
    setClient(text) {
      console.log(text);
    },
    save() {
      this.sale.total = this.$refs.total.value;
      console.log(this.$refs.total.value);
    },
    setTotal() {}
  },
  computed: {
    total() {
      return this.sale.products.reduce((prev, val, index) => {
        return prev + val.subtotal;
      }, 0);
    }
  }
};
</script>

<style lang="scss">
.main_sale__wrapper {
  padding-top: 55px;

  & hr {
    border-top-width: 3px;
  }
}

.main_sale__img {
  width: 60px;
  height: 100px;
}

.main_sale__title {
  text-align: left;
  font-size: 40px;
  font-weight: 600;
  margin-top: 20px;
}

.main_sale__content--padd {
  margin-top: 40px;
}

.main_sale__form {
  margin-top: 15px;
}

%button-form {
  border: 1px solid transparent;
  padding: 2px 10px 3px 10px;
  font-size: 22px;
  background-color: #35a8f9;
}
.main_sale__btn {
  @extend %button-form;
  font-weight: 600;
  margin-left: 14px;
}

.main_sale__btn-add {
  @extend %button-form;
  font-size: 16px;
  padding: 10px 35px 10px 35px;
}

.main_sale__btn-save {
  @extend %button-form;
  font-size: 16px;
  padding: 10px 35px 10px 35px;
  margin-top: 30px;
}

.main_sale__btn-close {
  @extend %button-form;
}

%input-form {
  display: inline;
  border: none;
  border-radius: 0px;
}

.main_sale__input {
  @extend %input-form;
  background-color: white !important;
  border: none !important;
  border-radius: 0px !important;
}

.main_sale__input-btn div {
  @extend %input-form;
  width: 80%;
}

.main_sale__wrapper-btn-add {
  margin-top: 25px;
  text-align: left;
}

.main_sale__wrapper-btn-close {
  margin-top: auto;
}

.main_sale {
  background-color: #f6f8fa;
  min-height: 100vh;

  & .main_sale--texts {
    text-align: left;
  }
}
</style>