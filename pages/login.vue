<template>
    <div id="content-container">

        <AppHeader />

        <main>
            <h1 id="content-title">Login</h1>
            <form id="login-form" action="">
                <div class="input-row-container">
                    <label for="">Username</label>
                    <div class="input-field-container">
                        <font-awesome-icon class="input-icon" :icon="['fas', 'user']"/>
                        <input type="text">
                    </div>
                </div>
                <div class="input-row-container">
                    <label for="">Password</label>
                    <div class="input-field-container">
                        <font-awesome-icon class="input-icon" :icon="['fas', 'lock']"/>
                        <input type="password">
                    </div>
                </div>
                <input type="submit" value="Login">
            </form>
        </main>
    </div>
</template>

<script>
import AppHeader from "../components/AppHeader"

export default {
  components: {
    AppHeader
  }
}
</script>

<style>
    #content-background{
        width: 40vw;
    }
    #login-form{
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 35px;
    }
    .input-row-container{
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    .input-row-container label{
        font-weight: bold;
    }
    .input-field-container{
        position: relative;
        width: 100%;
    }
    .input-icon{
        position: absolute;
        top: 5px;
        left: 5px;
    }
    .input-field-container input{
        padding: 5px 10px 5px 30px;
        height: 30px;
        width: 100%;
        background-color: transparent;
        border-bottom: 1px solid var(--grey);
    }
    .input-field-container input:focus{
        border-bottom: 3px solid var(--purple);
    }
    #login-form input[type=submit]{
        background-color: var(--purple);
        color: var(--white);
        font-size: 20px;
        font-weight: bold;
        margin: 30px 0px;
        height: 40px;
        border-radius: 4px;
    }
    #login-form input[type=submit]:hover{
        cursor: pointer;
        filter: brightness(110%);
    }
</style>