<template>
    <!-- Right Section -->
    <div class="right-section">
        <!-- Nav -->
        <div class="nav">
            <button ref="menubtn" @click="menuClick">
                <span class="material-symbols-sharp">
                    menu
                </span>
            </button>
            <div class="dark-mode" ref="darkmode" @click="darkModeToggle">
                <span class="material-symbols-sharp active" ref="light">
                    light_mode
                </span>
                <span class="material-symbols-sharp" ref="dark">
                    dark_mode
                </span>
            </div>

            <div class="profile">
                <div class="info">
                    <p>Hey, <b>Geva</b></p>
                    <small class="text-muted">Admin</small>
                </div>
                <div class="profile-img">
                    <img src="@/assets/images/dwon.avif" alt="">
                </div>
            </div>
        </div>
        <!-- End of Nav -->


        <div class="user-profile">
            <div class="logo">
                <img src="@/assets/images/logo.png" alt="">
                <h2>GevaDesign</h2>
                <p>Fullstack Web Dev</p>
            </div>
        </div>

        <!-- Reminders -->
        <div class="reminders">
            <div class="header">
                <h2>Reminders</h2>
                <span class="material-symbols-sharp">
                    notifications_none
                </span>
            </div>

            <div class="notification">
                <div class="icon">
                    <span class="material-symbols-sharp">
                        volume_up
                    </span>
                </div>
                <div class="content">
                    <h3>Wroksshop</h3>
                    <small class="text-muted">
                        08:00 AM - 12:00 PM
                    </small>
                </div>
                <span class="material-symbols-sharp">
                    more_vert
                </span>
            </div>

            <div class="notification deactive">
                <div class="icon">
                    <span class="material-symbols-sharp">
                        edit
                    </span>
                </div>
                <div class="content">
                    <h3>Wroksshop</h3>
                    <small class="text-muted">
                        08:00 AM - 12:00 PM
                    </small>
                </div>
                <span class="material-symbols-sharp">
                    more_vert
                </span>
            </div>

            <div class="notification add-reminder">
                <div>
                    <span class="material-symbols-sharp">
                        add
                    </span>
                    <h3>Add Reminder</h3>
                </div>
            </div>

        </div>
        <!-- End of Reminders -->

    </div>
</template>

<script>
export default {
    props: ['ShowMenu'],
    emits: ['show'],
    methods: {
        menuClick() {
            this.$emit('show')
        },
        darkModeToggle(){
            document.body.classList.toggle('dark-mode-variables')
            this.$refs.dark.classList.toggle('active')
            this.$refs.light.classList.toggle('active')
        }
    },

}
</script>

<style scoped>
.right-section {
    margin-top: 1.4rem;
}

.right-section .nav {
    display: flex;
    justify-content: end;
    gap: 2rem;
}

.right-section .nav button {
    display: none;
}

.right-section .dark-mode {
    background-color: var(--color-light);
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 1.6rem;
    width: 4.2rem;
    cursor: pointer;
    border-radius: var(--border-radius-1);
}

.right-section .dark-mode span {
    font-size: 1.2rem;
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.right-section .dark-mode span.active {
    background-color: var(--color-primary);
    color: white;
    border-radius: var(--border-radius-1);
}

.right-section .nav .profile {
    display: flex;
    gap: 2rem;
    text-align: right;
}

.right-section .nav .profile .profile-img {
    width: 2.8rem;
    height: 2.8rem;
    border-radius: 50%;
    overflow: hidden;
}

.right-section .user-profile {
    display: flex;
    justify-content: center;
    text-align: center;
    margin-top: 1rem;
    background-color: var(--color-white);
    padding: var(--card-padding);
    border-radius: var(--card-border-radius);
    box-shadow: var(--box-shadow);
    cursor: pointer;
    transition: all 0.3s ease;
}

.right-section .user-profile:hover {
    box-shadow: none;
}

.right-section .user-profile img {
    width: 11rem;
    height: auto;
    margin-bottom: 0.8rem;
    border-radius: 50%;
}

.right-section .user-profile h2 {
    margin-bottom: 0.2rem;
}

.right-section .reminders {
    margin-top: 2rem;
}

.right-section .reminders .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 0.8rem;
}

.right-section .reminders .header span {
    padding: 10px;
    box-shadow: var(--box-shadow);
    background-color: var(--color-white);
    border-radius: 50%;
}

.right-section .reminders .notification {
    background-color: var(--color-white);
    display: flex;
    align-items: center;
    gap: 1em;
    margin-bottom: 0.7em;
    padding: 1.4em var(--card-padding);
    border-radius: var(--border-radius-2);
    box-shadow: var(--box-shadow);
    cursor: pointer;
    translate: all 0.3s ease;
}

.right-section .reminders .notification:hover {
    box-shadow: none;
}

.right-section .reminders .notification .content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0;
    width: 100%;
}

.right-section .reminders .notification .icon {
    padding: 0.6em;
    color: var(--color-white);
    background-color: var(--color-success);
    border-radius: 20%;
    display: flex;
}

.right-section .reminders .notification.deactive .icon {
    background-color: var(--color-danger);
}

.right-section .reminders .add-reminder {
    background-color: var(--color-white);
    border: 2px dashed var(--color-primary);
    color: var(--color-primary);
    display: flex;
    align-items: center;
    justify-items: center;
    cursor: pointer;
}

.right-section .reminders .add-reminder:hover {
    background-color: var(--color-primary);
    color: white;
}

.right-section .reminders .add-reminder div {
    display: flex;
    align-items: center;
    gap: 0.6em;
}
</style>