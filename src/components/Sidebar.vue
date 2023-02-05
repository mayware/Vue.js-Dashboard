<template>
    <aside class="sidebar">
        <div class="sidebar-top">
            <div class="user-profile">
                <div class="user-logo">
                    <img src="../assets/logo.png" alt="" class="logo-image" />
                </div>
                <div class="user-name">Username</div>
            </div>
        </div>
        <div class="sidebar-middle">
            <ul class="sidebar-list">
                <li class="side-list-item">
                    <router-link to="/" class="side-item">
                        <span class="material-symbols-outlined"> home </span>
                        <span class="sidebar-link-title">Home</span>
                    </router-link>
                </li>
                <li class="side-list-item">
                    <router-link :to="{ name: 'about' }" class="side-item">
                        <span class="material-symbols-outlined"> help </span>
                        <span class="sidebar-link-title">About</span></router-link>
                </li>
                <li class="side-list-item">
                    <router-link :to="{ name: 'jobs' }" class="side-item">
                        <span class="material-symbols-outlined"> mail </span>
                        <span class="sidebar-link-title">Posts</span></router-link>
                </li>
                <li class="side-list-item">
                    <router-link :to="{ name: 'todo' }" class="side-item">
                        <span class="material-symbols-outlined"> task_alt </span>
                        <span class="sidebar-link-title">Todo app</span></router-link>
                </li>
            </ul>
        </div>
        <div class="sidebar-bottom">
            <ul class="sidebar-list">
                <li class="side-list-item">
                    <router-link :to="{ name: 'settings' }" class="side-item">
                        <span class="material-symbols-outlined"> settings </span>
                        <span class="sidebar-link-title">Settings</span>
                    </router-link>
                </li>
            </ul>
        </div>
    </aside>
</template>
<script>
export default {
}
</script>
<style scoped>
.sidebar {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: stretch;
    flex-shrink: 0;
    overflow-x: hidden;
    width: 65px;
    position: fixed;
    left: 0;
    top: 55px;
    bottom: 0;
    height: calc(100vh - 55px);
    border-right: 1px solid #343a40;
    background: #212529;
    transition: width 200ms ease-in-out;
}

.sidebar.open {
    width: 235px;
}

.sidebar .sidebar-top {
    display: flex;
    align-items: center;
    height: 4rem;
    transition: height 200ms ease-in-out;
}

.sidebar.open .sidebar-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 0 0.7rem;
    height: 5rem;
}

.user-profile {
    display: flex;
    align-items: center;
}

.sidebar .user-logo {
    -webkit-user-drag: none;
    display: block;
    border-radius: 50%;
    height: 45px;
    width: 45px;
    transition: 200ms ease-in-out;
}

.sidebar.open .user-logo {
    -webkit-user-drag: none;
    display: block;
    border-radius: 50%;
    height: 65px;
    width: 65px;
    transition: 200ms ease-in-out;
}

.sidebar .logo-image {
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    -webkit-user-drag: none;
    width: 100%;
    height: 100%;
}

.sidebar .user-name {
    display: none;
    font-size: 17px;
    font-weight: bold;
    color: #f8f9fa;
    margin-left: 1.2rem;
}

.sidebar.open .user-name {
    display: block;
}

.sidebar-middle {
    width: 100%;
    overflow-x: hidden;
    overflow-y: auto;
    flex-grow: 1;
    margin-bottom: 0.25rem;
    border-top: 2px solid #343a40;
}

.sidebar-bottom {
    width: 100%;
    margin-bottom: 0.25rem;
    border-top: 2px solid #343a40;
}

.sidebar-list {
    list-style: none;
    margin: 0;
    padding: 0;
}

.side-list-item {
    margin: 0.3rem;
    border-radius: 5px;
}

.sidebar .side-item {
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    color: #dee2e6;
    text-decoration: none;
    padding: .5rem;
    border-radius: 5px;
    width: 100%;
    transition: 200ms ease-in-out;
}

.sidebar.open .side-item {
    justify-content: flex-start;
}


.side-item:hover {
    background: #6c757d;
    color: #dee2e6;
    transition: 200ms ease-in-out;
}

.sidebar .side-item.router-link-exact-active {
    color: #f8f8f8;
    background-color: #284b63;
}

.sidebar-link-title {
    display: none;
    font-weight: 600;
    font-size: 16px;
    margin-left: 1.3rem;
    letter-spacing: 0.3mm;
}

.sidebar.open .sidebar-link-title {
    display: block;
}


@media(max-width: 620px) {
    .sidebar {
        width: 0;
    }
}
</style>