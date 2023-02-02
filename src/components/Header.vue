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
            <!-- <div class="header-links">
                <router-link to="/" class="header-link">Home</router-link>
                <router-link :to="{ name: 'about' }" class="header-link">About</router-link>
                <router-link :to="{ name: 'jobs' }" class="header-link">Jobs</router-link>
            </div> -->

        </div>
        <div class="header-right">
            <div class="login-section">
                <button class="login-btn">
                    <span class="material-symbols-outlined">person_filled</span>
                </button>
            </div>
            <!-- <button class="move-btn" @click="redirect">Redirect to Home Page</button>
            <button class="move-btn" @click="back">Go back</button>
            <button class="move-btn" @click="forward">Go forward</button> -->
        </div>

    </header>
</template>

<script>
export default {
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
</style>