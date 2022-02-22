<script>
import Intro from './Intro.vue';
export default {
    data() {
        return {
            email: '',
            password: '',
            passwordFieldType: "password",
            icon: 'bi-eye',
            robot: false,
            show: true,
        }
    },
    components: {
        Intro
    },
    methods: {
        clear() {
            this.email = ''
            this.password = ''
            this.robot = false
        },
        togglePassword() {
            this.passwordFieldType = this.passwordFieldType === "password" ? "text" : "password"
            this.icon = this.icon === "bi-eye" ? "bi-eye-slash" : "bi-eye"
        }
    },
    computed: {
        isDisabled() {
            const disabled = this.password.length < 6 || this.email.length < 7 || !this.robot
            return disabled;
        }
    }
}
</script>

<template>
    <div class="row">
        <div class="col-sm-12 col-md-4">
            <div class="row justify-content-center login m-4">
                <div class="card p-3">
                    <h1>Login</h1>
                    <form>
                        <div class="mb-3">
                            <label for="email" class="form-label">Email address</label>
                            <input
                                type="email"
                                v-model="email"
                                class="form-control"
                                id="email"
                                required
                            />
                        </div>
                        <label for="password" class="form-label">Password</label>
                        <div class="input-group mb-3">
                            <input
                                :type="passwordFieldType"
                                v-model="password"
                                class="form-control"
                                id="password"
                                minlength="6"
                                required
                            />
                            <span @click="togglePassword" class="input-group-text toggle">
                                <i :class="icon"></i>
                            </span>
                        </div>

                        <div class="mb-3 form-check">
                            <input
                                type="checkbox"
                                v-model="robot"
                                class="form-check-input"
                                id="robot"
                            />
                            <label class="form-check-label" for="robot">I am not a robot</label>
                        </div>
                        <div class="d-grid gap-2 col-12 mx-auto">
                            <button
                                :disabled="isDisabled"
                                class="btn btn-primary me-md-2"
                                type="submit"
                            >Login</button>
                            <button @click="clear" class="btn btn-light" type="button">Clear form</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>

        <div class="col-sm-12 col-md-8">
            <div class="row">
                <Intro />
            </div>
        </div>
    </div>
</template>

<style scoped>
.toggle {
    cursor: pointer;
}
.card {
    width: 18rem;
}
@media (min-width: 768px) { 
    .login {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
    }
}
</style>