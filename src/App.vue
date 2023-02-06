<script setup>
import { ref } from 'vue';
const isError = ref(false);
const firstName = ref('');
const lastName = ref('');
const email = ref('');
const password = ref('');
const firstNameError = ref(false);
const lastNameErr = ref(false);
const emailErr = ref(false);
const passwordErr = ref(false);
const handleSubmit = () => {
    if (firstName.value === '') {
        firstNameError.value = true;
    } else {
        firstNameError.value = false;
    }
    if (lastName.value === '') {
        lastNameErr.value = true;
    } else {
        lastNameErr.value = false;
    }
    const emailRegex = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
    const isEmailValid = emailRegex.test(email.value);
    if (email.value === '' || !isEmailValid) {
        emailErr.value = true;
    } else {
        emailErr.value = false;
    }
    if (password.value === '') {
        passwordErr.value = true;
    } else {
        passwordErr.value = false;
    }
};
const checkFirstName = () => {
    if (firstName.value === '') {
        firstNameError.value = true;
    } else {
        firstNameError.value = false;
    }
};
const checkLastName = () => {
    if (lastName.value === '') {
        lastNameErr.value = true;
    } else {
        lastNameErr.value = false;
    }
};
const checkEmail = () => {
    const emailRegex = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
    const isEmailValid = emailRegex.test(email.value);
    if (email.value === '' || !isEmailValid) {
        emailErr.value = true;
    } else {
        emailErr.value = false;
    }
};
const checkPassword = () => {
    if (password.value === '') {
        passwordErr.value = true;
    } else {
        passwordErr.value = false;
    }
};
</script>

<!-- ! html -->
<template>
    <div class="main_container">
        <div class="wrapper">
            <section class="text_container">
                <h1 class="title">Learn to code by watching others</h1>
                <p class="description">
                    See how experienced developers solve problems in real-time. Watching scripted tutorials is great,
                    but understanding how developers think is invaluable.
                </p>
            </section>
            <section class="contactAndTry_container">
                <a href="#" class="try_card"><span>Try it free 7 days</span> then $20/mo. thereafter </a>
                <form class="form" @submit.prevent="handleSubmit">
                    <div class="input_container">
                        <input
                            @input="checkFirstName"
                            :class="{ input_error: firstNameError }"
                            v-model="firstName"
                            type="text"
                            class="first_name"
                            placeholder="First Name"
                        /><img v-if="firstNameError" class="error_icon" src="./assets/images/icon-error.svg" />
                    </div>
                    <div v-if="firstNameError" class="error_message">First Name cannot be empty</div>
                    <div class="input_container">
                        <input
                            @input="checkLastName"
                            :class="{ input_error: lastNameErr }"
                            v-model="lastName"
                            type="text"
                            class="last_name"
                            placeholder="Last Name"
                        /><img v-if="lastNameErr" class="error_icon" src="./assets/images/icon-error.svg" />
                    </div>
                    <div v-if="lastNameErr" class="error_message">Last Name cannot be empty</div>
                    <div class="input_container">
                        <input
                            @input="checkEmail"
                            :class="{ input_error: emailErr }"
                            v-model="email"
                            type="text"
                            class="email"
                            placeholder="Email Address"
                        /><img v-if="emailErr" class="error_icon" src="./assets/images/icon-error.svg" />
                    </div>
                    <div v-if="emailErr" class="error_message">Looks like this is not an email</div>
                    <div class="input_container">
                        <input
                            @input="checkPassword"
                            :class="{ input_error: passwordErr }"
                            v-model="password"
                            type="password"
                            class="password"
                            placeholder="Password"
                        /><img v-if="passwordErr" class="error_icon" src="./assets/images/icon-error.svg" />
                    </div>
                    <div v-if="passwordErr" class="error_message">Password cannot be empty</div>
                    <button class="btn">CLAIM YOUR FREE TRIA</button>
                    <p class="terms">By clicking the button, you are agreeing to our <span>Terms and Services</span></p>
                </form>
            </section>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

//colors
$pink: #ff7979;
$dark_green: #38cc8b;
$green_btn_hover: #77e2b3;
$purple: #5e54a4;
$dark_color: #3d3b48;
$purple_text_color: #bab7d4;

.main_container {
    background: url('./assets/images/mobile_bg.png') no-repeat center center/cover;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-family: 'Poppins', sans-serif;
    min-height: 100vh;
    overflow: hidden;

    @media (min-width: 768px) {
        background: url('./assets/images/desktop_bg.png') no-repeat center center/cover;
    }

    .wrapper {
        padding: 88px 24px 68px 24px;
        max-width: 600px;

        @media (min-width: 768px) {
            max-width: 700px;
        }
        @media (min-width: 768px) {
            max-width: 900px;
        }
        @media (min-width: 1440px) {
            background: url('./assets/images/desktop_bg.png') no-repeat center center/cover;
            display: flex;
            max-width: 1380px;
        }
        .text_container,
        .contactAndTry_container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            flex: 1;
        }

        .text_container {
            @media (min-width: 1440px) {
                max-width: 525px;
            }
            .title {
                font-size: 28px;
                font-weight: 700;
                line-height: 36px;
                margin-bottom: 16px;
                color: white;
                @media (min-width: 768px) {
                    font-size: 40px;
                    line-height: 40px;
                }

                @media (min-width: 1440px) {
                    font-size: 50px;
                    line-height: 40px;
                    line-height: 55px;
                    text-align: left;
                }
            }
            .description {
                max-width: 400px;
                font-weight: 500;
                font-size: 16px;
                color: white;
                margin-bottom: 64px;
                line-height: 26px;
                @media (min-width: 768px) {
                    font-size: 24px;
                    line-height: 32px;
                    max-width: 60000px;
                }

                @media (min-width: 1440px) {
                    font-size: 16px;
                    line-height: 26px;
                    text-align: left;
                }
            }
        }
        .contactAndTry_container {
            .try_card {
                display: inline-block;
                color: white;
                text-decoration: none;
                font-weight: 400;
                line-height: 26px;
                padding: 18px 66px 18px 67px;
                background: #5e54a4;
                font-size: 15px;
                line-height: 26px;
                letter-spacing: 0.27px;
                border-radius: 10px;
                margin-bottom: 24px;
                box-shadow: 0px 8px 0px #00000025;
                width: 100%;
                @media (min-width: 768px) {
                    font-size: 18px;
                }

                span {
                    font-weight: 700;
                }
            }
            form {
                min-width: 327px;
                width: 100%;

                background-color: white;
                border-radius: 10px;
                padding: 24px;
                box-shadow: 0px 8px 0px #00000025;
                .input_container {
                    position: relative;
                    input {
                        width: 100%;
                        font-weight: 600;
                        font-size: 14px;
                        letter-spacing: 0.25px;
                        line-height: 26px;
                        margin-bottom: 16px;
                        opacity: 0.75;
                        border: 1px solid rgba(222, 222, 222, 1);
                        padding: 13px 18.5px;
                        border-radius: 5px;

                        @media (min-width: 768px) {
                            font-size: 18px;
                        }

                        &:focus,
                        &:active {
                            outline: none;
                        }
                    }
                    .error_icon {
                        position: absolute;
                        top: 16px;
                        right: 10px;
                    }
                    input.error {
                        border: 1px solid $pink;
                        color: $pink;
                    }
                }
                .error_message {
                    font-weight: 500;
                    font-size: 11px;
                    line-height: normal;
                    color: $pink;
                    text-align: right;
                    transform: translateY(-15px);
                    @media (min-width: 768px) {
                        font-size: 14px;
                    }
                }

                .btn {
                    display: block;
                    width: 100%;
                    margin-bottom: 16px;
                    background-color: $dark_green;
                    padding: 15px 45px;
                    border-radius: 5px;
                    border: none;
                    color: white;
                    box-shadow: inset 0px -4px 0px #00000017;
                    transition: all 0.3s ease-in-out;
                    &:hover {
                        background-color: $green_btn_hover;
                        cursor: pointer;
                    }
                    @media (min-width: 768px) {
                        font-size: 18px;
                    }
                }
                .terms {
                    font-weight: 500;
                    font-size: 11px;
                    line-height: 21px;
                    color: #bab7d4;
                    @media (min-width: 768px) {
                        font-size: 14px;
                    }

                    span {
                        color: $pink;
                        &:hover {
                            cursor: pointer;
                        }
                    }
                }
            }
        }
    }
}
</style>
