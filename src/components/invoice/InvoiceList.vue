<template>
  <div class="bg">
    <div class="item-list">
      <div class="barInvoice">
        <h1 class="textHead">Invoice</h1>
        <SearchBar class="srch"></SearchBar>
        <OrangeButton
          class="newV"
          @new-invoice-clicked="handleNewInvoiceClick"
        />
      </div>
      <div class="card-container">
        <CardIn v-for="index in 4" :key="index" />
      </div>

      <div class="header">
        <div
          style="display: flex; align-items: center; height: 50px; width: 20px"
        >
          <label class="checkbox">
            <input type="checkbox" @change="toggleAll" />
            <span class="checkmark"></span>
          </label>
        </div>
        <div>ID Invoice</div>
        <div>Due date</div>
        <div>Client</div>
        <div>Contact</div>
        <div>Amount</div>
        <div>Status</div>
      </div>
      <InvoiceItem
        v-for="invoice in invoices"
        :key="invoice.id"
        :invoice="invoice"
        :allChecked="allChecked"
      />

      <div class="footer">
        <div class="pagination-info">Showing 1-5 from 100 data</div>
        <div class="pagination-controls">
          <span class="previous-icon"><h3>&#10094;</h3></span>
          <div class="pagination-squares">
            <div class="squarePr">1</div>
            <div class="square">2</div>
            <div class="squareLs">3</div>
          </div>
          <span class="next-icon"><h3>&#10095;</h3></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import OrangeButton from "./OrangeButton.vue";
import CardIn from "./CardIn.vue";
import InvoiceItem from "./InvoiceItem.vue";
import SearchBar from "../SearchBar.vue";

export default {
  components: {
    InvoiceItem,
    SearchBar,
    OrangeButton,
    CardIn,
  },
  data() {
    return {
      allChecked: false,
      invoices: [
        {
          id: "#INV-0001234",
          date: "June 1, 2020, 08:22 AM",
          client: "Nella Vita",
          contact: "vita@mail.com",
          amount: "$650,036.34",
          status: "Completed",
        },
        {
          id: "#INV-0001234",
          date: "June 1, 2020, 08:22 AM",
          client: "Johnny Ahmad",
          contact: "ahmad@mail.com",
          amount: "$650,036.34",
          status: "Pending",
        },
        {
          id: "#INV-0001234",
          date: "June 10, 2021, 08:22 AM",
          client: "Tany Soap",
          contact: "soap@mail.com",
          amount: "$650,036.34",
          status: "Unpaid",
        },
        {
          id: "#INV-0001234",
          date: "June 10, 2021, 08:22 AM",
          client: "Tany Soap",
          contact: "soap@mail.com",
          amount: "$650,036.34",
          status: "Completed",
        },
        {
          id: "#INV-0001234",
          date: "June 10, 2021, 08:22 AM",
          client: "Tany Soap",
          contact: "soap@mail.com",
          amount: "$650,036.34",
          status: "Completed",
        },
        {
          id: "#INV-0001234",
          date: "June 10, 2021, 08:22 AM",
          client: "Tany Soap",
          contact: "soap@mail.com",
          amount: "$650,036.34",
          status: "Unpaid",
        },
        {
          id: "#INV-0001234",
          date: "June 10, 2021, 08:22 AM",
          client: "Tany Soap",
          contact: "soap@mail.com",
          amount: "$650,036.34",
          status: "Completed",
        },
      ],
      currentPage: 1,
    };
  },
  methods: {
    toggleAll() {
      this.allChecked = !this.allChecked;
    },
    handleNewInvoiceClick() {
      alert("New Invoice + clicked!");
      // Your custom logic here
    },
  },
};
</script>

<style scoped>
.header > div:nth-child(2) {
  width: 120px;
}
.header > div:nth-child(3) {
  width: 140px;
}
.header > div:nth-child(4) {
  width: 140px;
}
.header > div:nth-child(5) {
  width: 200px;
}
.header > div:nth-child(6) {
  width: 110px;
}
.textHead {
  margin-left: 25px;
  margin-top: 20px;
}

.item-list {
  font-family: "Arial", sans-serif;
}

.header {
  display: flex;
  align-items: center;
  font-weight: bold;
  gap: 40px;
  padding: 10px 20px;
  border-bottom: 1px solid #eaeaea;
}

.header input[type="checkbox"] {
  margin-right: 15px;
}

.item {
  display: flex;
  align-items: center;
  border-bottom: 1px solid #eaeaea;
}

.pagination {
  display: flex;
  justify-content: center;
  padding: 20px;
}

.pagination span {
  margin-right: 10px;
}

.pagination button {
  padding: 5px 15px;
  margin: 0 5px;
  border: 1px solid #dcdcdc;
  background-color: #f8f8f8;
  cursor: pointer;
}

.pagination button:hover {
  background-color: #eaeaea;
}

.pagination .page-number {
  padding: 5px 10px;
  margin: 0 5px;
  border: 1px solid #dcdcdc;
  background-color: #f8f8f8;
}

.pagination .page-number.active {
  background-color: #dcdcdc;
  font-weight: bold;
}
.barInvoice {
  display: flex;
}
.srch {
  margin-left: 560px;
  margin-top: 10px;
}
.newV {
  margin-left: 50px;
}
.item-list {
  margin-left: 100px;
}
.card-container {
  margin-left: 25px;
  margin-top: 25px;
  margin-bottom: 25px;
  display: flex;

  flex-wrap: wrap;
  gap: 80px;
}
.footer {
  display: flex;
  gap: 780px;
  align-items: center;
  padding: 10px 20px;
  border-top: 1px solid #eaeaea;
}

.pagination-info {
  font-size: 14px;
  color: #a2a2a2;
}

.pagination-controls {
  display: flex;
  align-items: center;
}

.pagination-squares {
  display: flex;
  gap: 5px;
}

.square {
  width: 30px;
  height: 30px;
  background-color: #f17b50;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
}
.squarePr {
  width: 30px;
  height: 30px;
  background-color: #efc5b6;
  color: #f17b50;
  display: flex;
  align-items: center;
  justify-content: center;
}
.squareLs {
  width: 30px;
  height: 30px;
  background-color: #efc5b6;
  color: #f17b50;
  display: flex;
  align-items: center;
  justify-content: center;
}

.pagination-icons {
  margin-left: auto;
}

.previous-icon,
.next-icon {
  cursor: pointer;
  margin: 0 10px;
  color: #97a0a9;
}
</style>
