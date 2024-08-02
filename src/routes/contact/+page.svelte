<script>
    const handleForm = () => {
        let nameInput = document.querySelector("#nameInput").value
        let emailInput = document.querySelector("#emailInput").value
        let messageInput = document.querySelector("#messageInput").value

        if (nameInput != "" && emailInput != "" && messageInput != "") {
            alert("We'll answer your message as soon as possible. Thank you for reaching out.")
            nameInput = "";
            emailInput = "";
            messageInput = "";
        } else {
            alert('You need to fill out all the fields.')
        }
    }
</script>

<svelte:head>
    <title>Contact me | Martin Leib</title>
    <meta name="description" content="Contact me" />
</svelte:head>

<form action="#" method="POST" class="container mt-5" on:submit|preventDefault={handleForm}>
    <div class="mb-3">
        <label for="nameInput" class="form-label">Your name</label>
        <input type="text" class="form-control" id="nameInput" required>
    </div>
    <div class="mb-3">
        <label for="emailInput" class="form-label">Your email address</label>
        <input type="email" class="form-control" id="emailInput" aria-describedby="emailHelp" required>
    </div>
    <div class="mb-3">
        <label for="messageInput" class="form-label">Message</label>
        <textarea class="form-control" id="messageInput" required></textarea>
    </div>
    <div class="d-flex justify-content-between align-items-center">
        <input type="submit" value="Send message" class="btn btn-primary">
        <span class="text-end">
            <label for="referRegister" class="ps-3 ps-sm-0">We'll never share your personal information with anyone else.</label>
        </span>
    </div>
</form>