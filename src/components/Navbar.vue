<template>
    <nav class="navbar is-primary" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
            <a class="navbar-item" >
                <img src="https://bulma.io/images/bulma-logo-white.png" width="112" height="28" alt="img">
            </a>

            <a role="button" :class="`navbar-burger ${isActive && 'is-active'}`" aria-label="menu" aria-expanded="false"
                data-target="navbarBasicExample" v-on:click="menuClick">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>

        <div id="navbarBasicExample" :class="`navbar-menu ${isActive && 'is-active'}`"
            :style="(isActive === true) && 'position: absolute; right: 0;'">
            <div class="navbar-start">
                <a class="navbar-item">
                    Home
                </a>

                <a class="navbar-item">
                    Documentation
                </a>

                <div class="navbar-item has-dropdown is-hoverable">
                    <span class="navbar-link" v-on:click="dropdownClick">
                        More
                    </span>

                    <div class="navbar-dropdown" :style="(isActiveDropDown === false) && 'display: none'">
                        <a class="navbar-item">
                            About
                        </a>
                        <a class="navbar-item">
                            Jobs
                        </a>
                        <a class="navbar-item">
                            Contact
                        </a>
                        <hr class="navbar-divider">
                        <a class="navbar-item">
                            Report an issue
                        </a>
                    </div>
                </div>
            </div>

            <div class="navbar-end">
                <div class="navbar-item">
                    <div class="buttons">
                        <a class="button is-primary">
                            <strong>Sign up</strong>
                        </a>
                        <a class="button is-light">
                            Log in
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            isActive: false,
            isActiveDropDown: true,
        }
    },
    methods: {
        menuClick() {
            this.isActive = !this.isActive
        },
        dropdownClick() {
            this.isActiveDropDown = !this.isActiveDropDown
        }
    },
}
</script>