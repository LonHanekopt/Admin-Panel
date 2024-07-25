<template>
     <!-- main content -->
     <main>
      <h1>Analytics</h1>
      <!-- Analytics -->
      <div class="analyse">
        <div class="sales">
          <div class="status">
            <div class="info">
              <h3>Total Sales</h3>
              <h1>$65,024</h1>
            </div>
            <div class="progress">
              <svg>
                <circle cx="38" cy="38" r="36"></circle>
              </svg>
              <div class="percentage">
                <p>+81%</p>
              </div>
            </div>
          </div>
        </div>
        <div class="visits">
          <div class="status">
            <div class="info">
              <h3>Site Visits</h3>
              <h1>16,313</h1>
            </div>
            <div class="progress">
              <svg>
                <circle cx="38" cy="38" r="36"></circle>
              </svg>
              <div class="percentage">
                <p>-12%</p>
              </div>
            </div>
          </div>
        </div>
        <div class="searches">
          <div class="status">
            <div class="info">
              <h3>Searches</h3>
              <h1>15,009</h1>
            </div>
            <div class="progress">
              <svg>
                <circle cx="38" cy="38" r="36"></circle>
              </svg>
              <div class="percentage">
                <p>+2%</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- End of Analytics -->

      <!-- New Users -->
      <div class="new-users">
        <h2>New Users</h2>
        <div class="user-list">
          <div class="user">
            <img src="@/assets/images/dwon.avif" alt="">
            <h2>Emir</h2>
            <p>54 Min Ago</p>
          </div>
          <div class="user">
            <img src="@/assets/images/emily.jpeg" alt="">
            <h2>Emily</h2>
            <p>21 Min Ago</p>
          </div>
          <div class="user">
            <img src="@/assets/images/lisa.jpeg" alt="">
            <h2>Lisa</h2>
            <p>4 Hours Ago</p>
          </div>
          <div class="user">
            <img src="@/assets/images/tery.png" alt="">
            <h2>Tery</h2>
            <p>8 Hours Ago</p>
          </div>
        </div>
      </div>
      <!-- End of New Users -->


      <!-- Recent Orders -->
      <div class="recent-orders">
        <h2>Recent Orders</h2>
        <table>
          <thead>
            <tr>
              <th>Course Name</th>
              <th>Course Number</th>
              <th>Payment Method</th>
              <th>Payment</th>
              <th>Status</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="order in orders" :key="order.productName">
              <td>{{ order.productName }}</td>
              <td>{{ order.productNumber }}</td>
              <td>{{ order.paymentMethod }}</td>
              <td>{{ order.paymentStatus }}</td>
              <td :class="order.status === 'Pending' ? 'warning' :
                order.status === 'Shipped' ? 'success' :
                  order.status === 'Completed' ? 'success' :
                    order.status === 'Processing' ? 'primary' : 'danger'
                ">{{ order.status }}</td>
              <td class="primary">Details</td>
            </tr>
          </tbody>
        </table>
        <a href="">Show All</a>
      </div>
      <!-- End of Recent Orders -->
    </main>
    <!-- End of Main Content -->
</template>

<script>
    export default {
        props: ['orders']
    }
</script>

<style scoped>
main {
    margin-top: 1.4rem;

}

main .analyse {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.6rem;
}

main .analyse>div {
    background-color: var(--color-white);
    padding: var(--card-padding);
    border-radius: var(--card-border-radius);
    margin-top: 1rem;
    box-shadow: var(--box-shadow);
    cursor: pointer;
    transition: all 0.3s ease;
}

main .analyse>div:hover {
    box-shadow: none;
}

main .analyse>div .status {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

main .analyse h3 {
    margin-left: 0.6rem;
    font-size: 1rem;
}

main .analyse .progress {
    position: relative;
    width: 92px;
    height: 92px;
    border-radius: 50%;
}

main .analyse svg {
    width: 7rem;
    height: 7rem;
}

main .analyse svg circle {
    fill: none;
    stroke-width: 10;
    stroke-linecap: round;
    transform: translate(5px, 5px);
}

main .analyse .sales svg circle {
    stroke: var(--color-success);
    stroke-dashoffset: -30;
    stroke-dasharray: 200;
}

main .analyse .visits svg circle {
    stroke: var(--color-danger);
    stroke-dashoffset: -30;
    stroke-dasharray: 200;
}

main .analyse .searches svg circle {
    stroke: var(--color-primary);
    stroke-dashoffset: -30;
    stroke-dasharray: 200;
}

main .analyse .progress .percentage {
    position: absolute;
    top: -3px;
    left: -1px;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    width: 100%;
}

main .new-users {
    margin-top: 1.3rem;
}

main .new-users .user-list {
    background-color: var(--color-white);
    padding: var(--card-padding);
    border-radius: var(--card-border-radius);
    margin-top: 1rem;
    box-shadow: var(--box-shadow);
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 1.4rem;
    cursor: pointer;
    transition: all 0.3s ease;
}

main .new-users .user-list:hover {
    box-shadow: none;
}

main .new-users .user-list .user {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

main .new-users .user-list .user img {
    width: 5rem;
    height: 5rem;
    margin-bottom: 0.4rem;
    border-radius: 50%;
}

main .recent-orders {
    margin-top: 1.3rem;
}

main .recent-orders h2 {
    margin-top: 0.8rem;
}

main .recent-orders table {
    background-color: var(--color-white);
    width: 100%;
    padding: var(--card-padding);
    text-align: center;
    box-shadow: var(--box-shadow);
    border-radius: var(--card-border-radius);
    transition: all 0.3s ease;
}

main .recent-orders table:hover {
    box-shadow: none;
}

main table tbody td {
    height: 2.8rem;
    border-bottom: 1px solid var(--color-light);
    color: var(--color-dark-variant);
}

main table tbody tr:last-child td {
    border: none;
}

main .recent-orders a {
    text-align: center;
    display: block;
    margin: 1rem auto;
    color: var(--color-primary);
}
</style>