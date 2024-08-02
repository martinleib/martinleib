<form action="#" method="post" class="container mt-5" on:submit|preventDefault>
    <div class="mb-3">
        <label for="emailInput" class="form-label">Email address</label>
        <input type="email" class="form-control" id="emailInput" aria-describedby="emailHelp" required>
    </div>
    <div class="mb-3">
        <label for="passwordInput" class="form-label">Password</label>
        <input type="password" class="form-control" id="passwordInput" required>
    </div>
    <div class="d-flex justify-content-between align-items-center">
        <input type="submit" value="Login" class="btn btn-primary">
        <span class="text-end">
            <label for="referRegister">Don't have an account?</label>
            <br />
            <a href="/register" id="referRegister">Create an account</a>
        </span>
    </div>
</form>