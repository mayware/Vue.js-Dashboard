<template>
    <div class="content-settings">
        <!-- <div class="content-title">Settings</div> -->
        <div class="settings-box" id="userDescription">
            <span class="config-title">Account</span>
            <div class="set-config">
                <div class="profile-imgage">
                    <img src="../assets/logo.png" alt="profile-image" class="acc-img">
                </div>
                <div class="profile-desc">
                    <div class="user-detail">
                        <span class="credential-selector">Name:</span>
                        <div class="selector">Jim Carrey</div>
                    </div>
                    <div class="user-detail">
                        <span class="credential-selector">username:</span>
                        <div class="selector">@jim_carrey</div>
                    </div>
                    <div class="user-detail">
                        <span class="credential-selector">Email:</span>
                        <div class="selector">jim_carrey@mailbox.com</div>
                    </div>
                    <div class="user-detail">
                        <span class="credential-selector">Profile created:</span>
                        <div class="selector">03.02.2023</div>
                    </div>
                </div>
            </div>
        </div>
        <div class="settings-box" id="userSubsriptions">
            <span class="config-title">Subscriptions</span>
            <div class="set-config">You have'n got any subscriptions</div>
        </div>
        <div class="settings-box">
            <span class="config-title">Privacy</span>
            <div class="privacy-set-config">
                <button class="privacy-btn">Change email</button>
                <button class="privacy-btn">Change password</button>
                <button class="privacy-btn">Block users</button>
                <button class="privacy-btn">Change username</button>
                <button class="privacy-btn">Delete account</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Settings',
}
</script>
<style scoped>
.content-settings {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    padding: .5rem;
}

.content-title {
    display: flex;
    align-items: center;
    font-size: 26px;
    font-weight: 700;
    color: #dee2e6;
    margin-bottom: .5rem;
}

.settings-box {
    display: flex;
    flex-direction: column;
    padding: 1rem;
    background: #202020;
    border-radius: 10px;
    width: 100%;
}

.config-title {
    font-size: 20px;
    font-weight: 500;
    color: #dee2e6;
    margin-bottom: 1rem;
}

#userDescription {
    grid-column: 1/ 4;
}

#userSubsriptions {
    grid-column: 1 / 3;
}

.set-config {
    display: flex;
    align-items: center;
}

.privacy-set-config {
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
}

.privacy-btn {
    display: flex;
    align-items: center;
    padding: .5rem;
    background: #495057;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin: .3rem;
    font-size: 16px;
    font-weight: 500;
    color: #dee2e6;
}

.profile-imgage {
    background-color: #343434;
    border-radius: 5px;
    height: 150px;
    width: 150px;
}

.profile-desc {
    display: flex;
    flex-direction: column;
    padding: .5rem;
    /* border: 1px solid #343434; */
    margin: .5rem;
}

.user-detail {
    display: flex;
    align-items: center;
}

.credential-selector {
    font-size: 20px;
    font-weight: 500;
    color: #0077b6;
    margin-right: .5rem;
}

.selector {
    font-size: 22px;
    color: #adb5bd;
    font-weight: 500;
}

.profile-extra {
    display: flex;
    align-items: center;
    flex-direction: column;
    padding: .5rem;
    border: 1px solid #343434;
}

.acc-img {
    height: 100%;
    width: 100%;
}
</style>