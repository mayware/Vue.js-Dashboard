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
                        <a href="#" class="dropdown-link">Account</a>
                        <a href="#" class="dropdown-link">Settings</a>
                        <a href="#" class="dropdown-link">Log out</a>
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
    background: #1b263b;
    position: fixed;
    top: 0;
    width: 100%;
    height: 65px;
    padding: 0 1.5rem;
    box-shadow: 0 2px 10px 0 rgb(0, 0, 0, .4);
}

.header-left {
    display: flex;
    align-items: center;
}

.sidebar-btn,
.login-btn {
    cursor: pointer;
    background: none;
    border: none;
    color: #dee2e6;
    transition: 200ms ease-in-out;
}

.sidebar-btn:hover,
.login-btn:hover,
.header-title:hover {
    color: #adb5bd;
    transition: 200ms ease-in-out;
}

.header-title {
    color: #dee2e6;
    font-size: 24px;
    font-weight: 700;
    margin: 1rem;
    transition: 200ms ease-in-out;
}

.home-link {
    text-decoration: none;
}

.move-btn {
    padding: .5rem;
    border: none;
    border-radius: 5px;
    background: #00754a;
    color: #dee2e6;
    cursor: pointer;
    margin: .1rem;
    transition: 200ms ease-in-out;
}

.dropdown-menu {
    position: absolute;
    top: 50px;
    right: 25px;
    display: flex;
    align-items: center;
    flex-direction: column;
    background: #202020;
    border: 1px solid #343434;
    border-radius: 5px;
    width: 150px;
}

.dropdown-link {
    text-align: center;
    text-decoration: none;
    color: #adb5bd;
    padding: .5rem;
    height: 100%;
    width: 100%;
}

.dropdown-link:hover {
    background: #343434;
}
</style>