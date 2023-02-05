<template>
    <header class="header">
        <div class="header-left">
            <div class="sidebar-toggler">
                <button class="sidebar-btn" @click="$emit('tog')">
                    <span class="material-symbols-outlined">menu</span>
                </button>
            </div>
            <router-link to="/" class="home-link">
                <div class="header-title">Dashboard</div>
            </router-link>
        </div>
        <div class="header-right">
            <div class="login-section">
                <button class="login-btn" @click="dropdownToggler">
                    <span class="material-symbols-outlined">person_filled</span>
                </button>
                <div class="dropdown">
                    <div class="dropdown-menu" v-if="show">
                        <router-link to="/account" class="dropdown-link">
                            Account
                            <span class="material-symbols-outlined"> person_filled </span>
                        </router-link>
                        <router-link to="/settings" class="dropdown-link">
                            Settings
                            <span class="material-symbols-outlined"> settings </span>
                        </router-link>
                        <router-link to="/logout" class="dropdown-link">
                            Log out
                            <span class="material-symbols-outlined"> logout </span>
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            show: false
        }
    },
    methods: {
        dropdownToggler() {
            this.show = !this.show
        },
        close(e) {
            if (!this.$el.querySelector('.login-btn').contains(e.target)) {
                this.show = false
            }
        },
    },
    mounted() {
        document.addEventListener('click', this.close)
    },
    beforeDestroy() {
        document.removeEventListener('click', this.close)
    }
}

</script>

<style scoped>
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.5rem;
    background: #0A2647;
    position: fixed;
    top: 0;
    width: 100%;
    height: 55px;
    padding: 0 1.5rem 0 .6rem;
    box-shadow: 0 2px 10px 0 rgb(0, 0, 0, .4);
}

.header-left {
    display: flex;
    align-items: center;
}

.sidebar-btn,
.login-btn {
    display: flex;
    align-items: center;
    cursor: pointer;
    background: none;
    border: none;
    border-radius: 50%;
    padding: .7rem;
    color: #dee2e6;
    transition: 200ms ease-in-out;
}

.sidebar-btn:hover {
    color: #adb5bd;
    transition: 200ms ease-in-out;
}

.login-btn:hover,
.header-title:hover {
    color: #adb5bd;
    transition: 200ms ease-in-out;
}

.header-title {
    color: #dee2e6;
    font-size: 24px;
    font-weight: 700;
    margin: .5rem;
    transition: 200ms ease-in-out;
}

.home-link {
    text-decoration: none;
}

.dropdown-menu {
    position: absolute;
    top: 50px;
    right: 25px;
    display: flex;
    flex-direction: column;
    background: #202020;
    border: 1px solid #343434;
    border-radius: 5px;
    width: 150px;
}

.dropdown-link {
    display: flex;
    align-items: center;
    justify-content: space-between;
    text-decoration: none;
    color: #adb5bd;
    padding: .5rem;
}

.dropdown-link:hover {
    background: #343434;
}
</style>