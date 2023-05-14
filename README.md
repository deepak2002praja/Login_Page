<html>

<head>

    <script>
        const form = document.querySelector("form");
        eField = form.querySelector(".email"),
            eInput = eField.querySelector("input"),
            pField = form.querySelector(".password"),
            pInput = pField.querySelector("input");

        form.onsubmit = (e) => {
            e.preventDefault();
            (eInput.value == "") ? eField.classList.add("shake", "error"): checkEmail();
            (pInput.value == "") ? pField.classList.add("shake", "error"): checkPass();

            setTimeout(() => {
                eField.classList.remove("shake");
                pField.classList.remove("shake");
            }, 500);

            eInput.onkeyup = () => {
                checkEmail();
            }
            pInput.onkeyup = () => {
                checkPass();
            }

            function checkEmail() {
                let pattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
                if (!eInput.value.match(pattern)) {
                    eField.classList.add("error");
                    eField.classList.remove("valid");
                    let errorTxt = eField.querySelector(".error-txt");

                    (eInput.value != "") ? errorTxt.innerText = "Enter a valid email address": errorTxt.innerText = "Email can't be blank";
                } else {
                    eField.classList.remove("error");
                    eField.classList.add("valid");
                }
            }

            function checkPass() {
                if (pInput.value == "") {
                    pField.classList.add("error");
                    pField.classList.remove("valid");
                } else {
                    pField.classList.remove("error");
                    pField.classList.add("valid");
                }
            }
            if (!eField.classList.contains("error") && !pField.classList.contains("error")) {
                window.location.href = form.getAttribute("action");
            }
        }
    </script>


    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Poppins", sans-serif;
        }
        
        body {
            width: 100%;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #5372F0;
        }
        
         ::selection {
            color: #fff;
            background: #5372F0;
        }
        
        .wrapper {
            width: 380px;
            padding: 40px 30px 50px 30px;
            background: #fff;
            border-radius: 5px;
            text-align: center;
            box-shadow: 10px 10px 15px rgba(0, 0, 0, 0.1);
        }
        
        .wrapper header {
            font-size: 35px;
            font-weight: 600;
        }
        
        .wrapper form {
            margin: 40px 0;
        }
        
        form .field {
            width: 100%;
            margin-bottom: 20px;
        }
        
        form .field.shake {
            animation: shake 0.3s ease-in-out;
        }
        
        @keyframes shake {
            0%,
            100% {
                margin-left: 0px;
            }
            20%,
            80% {
                margin-left: -12px;
            }
            40%,
            60% {
                margin-left: 12px;
            }
        }
        
        form .field .input-area {
            height: 50px;
            width: 100%;
            position: relative;
        }
        
        form input {
            width: 100%;
            height: 100%;
            outline: none;
            padding: 0 45px;
            font-size: 18px;
            background: none;
            caret-color: #5372F0;
            border-radius: 5px;
            border: 1px solid #bfbfbf;
            border-bottom-width: 2px;
            transition: all 0.2s ease;
        }
        
        form .field input:focus,
        form .field.valid input {
            border-color: #5372F0;
        }
        
        form .field.shake input,
        form .field.error input {
            border-color: #dc3545;
        }
        
        .field .input-area i {
            position: absolute;
            top: 50%;
            font-size: 18px;
            pointer-events: none;
            transform: translateY(-50%);
        }
        
        .input-area .icon {
            left: 15px;
            color: #bfbfbf;
            transition: color 0.2s ease;
        }
        
        .input-area .error-icon {
            right: 15px;
            color: #dc3545;
        }
        
        form input:focus~.icon,
        form .field.valid .icon {
            color: #5372F0;
        }
        
        form .field.shake input:focus~.icon,
        form .field.error input:focus~.icon {
            color: #bfbfbf;
        }
        
        form input::placeholder {
            color: #bfbfbf;
            font-size: 17px;
        }
        
        form .field .error-txt {
            color: #dc3545;
            text-align: left;
            margin-top: 5px;
        }
        
        form .field .error {
            display: none;
        }
        
        form .field.shake .error,
        form .field.error .error {
            display: block;
        }
        
        form .pass-txt {
            text-align: left;
            margin-top: -10px;
        }
        
        .wrapper a {
            color: #5372F0;
            text-decoration: none;
        }
        
        .wrapper a:hover {
            text-decoration: underline;
        }
        
        form input[type="submit"] {
            height: 50px;
            margin-top: 30px;
            color: #fff;
            padding: 0;
            border: none;
            background: #5372F0;
            cursor: pointer;
            border-bottom: 2px solid rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        form input[type="submit"]:hover {
            background: #2c52ed;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <header>Login Form</header>
        <form action="#">
            <div class="field email">
                <div class="input-area">
                    <input type="text" placeholder="Email Address">
                    <i class="icon fas fa-envelope"></i>
                    <i class="error error-icon fas fa-exclamation-circle"></i>
                </div>
                <div class="error error-txt">Email can't be blank</div>
            </div>
            <div class="field password">
                <div class="input-area">
                    <input type="password" placeholder="Password">
                    <i class="icon fas fa-lock"></i>
                    <i class="error error-icon fas fa-exclamation-circle"></i>
                </div>
                <div class="error error-txt">Password can't be blank</div>
            </div>
            <div class="pass-txt"><a href="#">Forgot password?</a></div>
            <input type="submit" value="Login">
        </form>
        <div class="sign-txt">Not yet member? <a href="#">Signup now</a></div>
    </div>


</body>
<script>
    className = "elup"
    IdleDeadline = AbortSignal
</script>

</html>
