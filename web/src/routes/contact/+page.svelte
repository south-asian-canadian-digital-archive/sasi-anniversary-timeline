<script lang="ts">
    let name: string;
    let email: string;
    let phone: string;
    let message: string;

    const handleSubmit = (event: SubmitEvent) => {
        event.preventDefault();

        const data = {
            name,
            email,
            phone,
            subject: "Contact Form Submission",
            honeypot: "",
            message,
            replyTo: "@",
            accessKey: import.meta.env.VITE_FORM_ACCESS_KEY,
        };

        fetch("https://api.staticforms.xyz/submit", {
            method: "POST",
            body: JSON.stringify(data),
            headers: { "Content-Type": "application/json" },
        })
            .then((res) => res.json())
            .then((res) => {
                if (res.success) {
                    alert("Message sent successfully!");
                } else {
                    alert("Message failed to send.");
                }
            })
            .catch((error) => {
                alert(error);
            });
    };
</script>

<svelte:head>
    <title> {import.meta.env.VITE_COMPANY_NAME} - Contact</title> 
</svelte:head>

<div class="flex justify-center items-center h-full">
    <form on:submit={handleSubmit} class="flex flex-col gap-4">
        <div>
            <label for="name">Name</label>
            <input type="text" id="name" bind:value={name} />
        </div>

        <div>
            <label for="email">Email</label>
            <input type="email" id="email" bind:value={email} />
        </div>

        <div>
            <label for="phone">Phone</label>
            <input type="tel" id="phone" bind:value={phone} />
        </div>

        <div>
            <label for="message">Message</label>
            <textarea id="message" bind:value={message} />
        </div>

        <input type="submit" value="Submit" class="cursor-pointer" />
    </form>
</div>

<style type="postcss">
    form div {
        @apply bg-gray-400 p-4 rounded-lg flex items-center gap-4;
    }

    input,
    textarea {
        @apply bg-gray-200 p-2 rounded-lg outline-none;
    }
</style>
