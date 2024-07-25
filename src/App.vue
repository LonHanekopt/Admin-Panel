<template>
  <div class="container">
    <sidebar :showMenu="showMenu" @close="closeMenu"></sidebar>
    <maincontent :orders="orders"></maincontent>
    <rightsection :showMenu="showMenu" @show="openMenu"></rightsection>
  </div>
</template>

<script>
import sidebar from '@/components/TheAside'
import maincontent from '@/components/TheMain'
import rightsection from '@/components/TheRightSection'

export default {
  name: 'App',
  components: {
    sidebar,
    maincontent,
    rightsection
  },
  data() {
    return {
      showMenu: false,
      orders: [
        {
          productName: "Tech Product",
          productNumber: "1312",
          paymentMethod: "Debit Card",
          paymentStatus: "Due",
          status: "Pending",
        },
        {
          productName: "Gadget Gizmo",
          productNumber: "2456",
          paymentMethod: "Credit Card",
          paymentStatus: "Paid",
          status: "Shipped",
        },
        {
          productName: "Smart Device",
          productNumber: "7890",
          paymentMethod: "Payoneer",
          paymentStatus: "Pending",
          status: "Processing",
        },
        {
          productName: "Electronic Widget",
          productNumber: "1122",
          paymentMethod: "Bank Transfer",
          paymentStatus: "Due",
          status: "Pending",
        },
        {
          productName: "Digital Widget",
          productNumber: "3321",
          paymentMethod: "Cryptocurrency",
          paymentStatus: "Paid",
          status: "Completed",
        },
        {
          productName: "Innovative Device",
          productNumber: "5544",
          paymentMethod: "E-wallet",
          paymentStatus: "Refunded",
          status: "Failed",
        },
        {
          productName: "Smart Appliance",
          productNumber: "9988",
          paymentMethod: "Credit Card",
          paymentStatus: "Paid",
          status: "Shipped",
        },
      ],
    }
  },
  methods: {
    openMenu(){
      this.showMenu = true;
    },
    closeMenu(){
      this.showMenu = false;
    }
  }
}
</script>

<style></style>
