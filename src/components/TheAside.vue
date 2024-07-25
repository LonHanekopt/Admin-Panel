<template>
  <!-- sidebar -->
  <aside ref="aside">
    <div class="toggle">
      <div class="logo">
        <img src="@/assets/images/logo.png" alt="">
        <h2>Geva<span class="danger">Designs</span></h2>
      </div>
      <div class="close" ref="closebtn" @click="closeMenu">
        <span class="material-symbols-sharp">
          close
        </span>
      </div>
    </div>

    <div class="sidebar">
      <a href="">
        <span class="material-symbols-sharp">
          dashboard
        </span>
        <h3>Dashboard</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          person_outline
        </span>
        <h3>Users</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          receipt_long
        </span>
        <h3>History</h3>
      </a>
      <a href="" class="active">
        <span class="material-symbols-sharp">
          insights
        </span>
        <h3>ANalytics</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          mail_outline
        </span>
        <h3>Tickets</h3>
        <span class="message-count">27</span>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          inventory
        </span>
        <h3>Sale Lististory</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          report_gmailerrorred
        </span>
        <h3>Reports</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          settings
        </span>
        <h3>Settings</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          add
        </span>
        <h3>New Login</h3>
      </a>
      <a href="">
        <span class="material-symbols-sharp">
          logout
        </span>
        <h3>Logout</h3>
      </a>
    </div>
  </aside>
  <!-- End of Sidebar -->
</template>

<script>
export default {
  props: ['showMenu'],
  emits: ['close'],
  watch: {
    showMenu() {
      if (this.showMenu)
        this.$refs.aside.style.display = 'block'
      else
        this.$refs.aside.style.display = 'none'
    }
  },
  methods: {
    closeMenu() {
      this.$emit('close')
    }
  }
}
</script>

<style scoped>
aside {
  height: 100vh;
}

aside .toggle {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 1.4rem;
}

aside .toggle .logo {
  display: flex;
  gap: 0.5rem;
}

aside .toggle .logo img {
  width: 2rem;
  height: 2rem;
}

aside .toggle .close {
  padding-right: 1rem;
  display: none;
}

aside .sidebar {
  position: relative;
  display: flex;
  flex-direction: column;
  background-color: var(--color-white);
  box-shadow: var(--box-shadow);
  border-radius: 15px;
  height: 88vh;
  transition: all 0.3s ease;
}

aside .sidebar:hover {
  box-shadow: none;
}

aside .sidebar a {
  display: flex;
  align-items: center;
  color: var(--color-info-dark);
  height: 3.7rem;
  gap: 1rem;
  position: relative;
  margin-left: 2rem;
  transition: all 0.3s ease;
}

aside .sidebar a span {
  font-size: 1.6rem;
  transition: all 0.3s ease;
}

aside .sidebar a:last-child {
  position: absolute;
  bottom: 10px;
  width: 100%;
}

aside .sidebar a.active {
  width: 100%;
  color: var(--color-primary);
  background-color: var(--color-light);
  margin-left: 0;
}

aside .sidebar a.active::before {
  content: '';
  width: 6px;
  height: 18px;
  background-color: var(--color-primary);
}

aside .sidebar a.active span {
  color: var(--color-primary);
  margin-left: calc(1rem - 3px);
}

aside .sidebar a:hover {
  color: var(--color-primary);
}

aside .sidebar a:hover span {
  margin-left: 0.6rem;
}

aside .sidebar .message-count {
  background-color: var(--color-danger);
  padding: 2px 6px;
  color: var(--color-white);
  border-radius: var(--border-radius-1);
  font-size: 11px;
}
</style>