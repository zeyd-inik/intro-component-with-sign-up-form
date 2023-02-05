<script setup></script>

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
                <!-- ! html -->
                <form class="form">
                    <input type="text" class="first_name" placeholder="First Name" />
                    <input type="text" class="last_name" placeholder="Last Name" />
                    <input type="text" class="email" placeholder="Email Address" />
                    <input type="password" class="password" placeholder="Password" />
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

    .wrapper {
        padding: 88px 24px 68px 24px;

        .text_container {
            .title {
                font-size: 28px;
                font-weight: 700;
                line-height: 36px;
                margin-bottom: 16px;
                color: white;
            }
            .description {
                font-weight: 500;
                font-size: 16px;
                color: white;
                margin-bottom: 64px;
                line-height: 26px;
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

                span {
                    font-weight: 700;
                }
            }
            form {
                width: 327px;
                height: 442px;
                background-color: white;
                border-radius: 10px;
                padding: 24px;
                box-shadow: 0px 8px 0px #00000025;
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
                    &:focus,
                    &:active {
                        outline: none;
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
                }
                .terms {
                    font-weight: 500;
                    font-size: 11px;
                    line-height: 21px;
                    color: #bab7d4;
                    span {
                        color: $pink;
                    }
                }
            }
        }
    }
}
</style>
