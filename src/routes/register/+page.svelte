<form action="#" method="post" class="container mt-5" id="registerForm" on:submit|preventDefault>
    <div class="mb-3">
        <label for="emailInput" class="form-label">Email address</label>
        <input type="email" class="form-control" id="emailInput" aria-describedby="emailHelp" required>
        <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
    </div>
    <div class="mb-3">
        <label for="passwordInput" class="form-label">Password</label>
        <input type="password" class="form-control" id="passwordInput" required>
    </div>
    <div class="d-flex justify-content-between align-items-center">
        <input type="submit" value="Register" class="btn btn-primary">
        <span class="text-end">
            <label for="referLogin">Already have an account?</label>
            <br />
            <a href="/login" id="referLogin">Login</a>
        </span>
    </div>
</form>