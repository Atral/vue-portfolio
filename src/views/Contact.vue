<script setup>

</script>

<template>
    <div class="section" id="contact">
        <h2 class="section-title">Contact</h2>
        <form action="https://formcarry.com/s/FH4QQCkVmV3" method="POST" >
            <input type="text" class="name" name="fullName" id="fullName" placeholder="Your Name"/>
            <input type="email" name="email" id="email" placeholder="Your Email" />
            <textarea placeholder="Message" name="message" id="message" cols="30" rows="6" />
            <button type="submit">Send</button>
        </form>
    </div>
</template>

<style scoped>
    #contact {
        padding: 1rem;
        form {
            all: unset;
            display: flex;
            flex-direction: column;
            gap: 1rem;

            input, textarea {
                all: unset;
                background-color: transparent;
                border: 0;
                padding: 1rem;
                color: var(--header-text);
                border: 1px solid rgba(0, 190, 243, 0.2039215686);
                border-radius: 0.3rem;
                transition: border-color 0.2s ease-in-out;
            }

            input:hover, textarea:hover {
                border-color: rgba(0, 190, 243, 0.342);
            }

            input:focus, textarea:focus {
                border-color: rgba(0, 190, 243, 0.486);
            }

            button {
                all: unset;
                padding: 0.5rem;
                /* background-color: rgba(0, 190, 243, 0.342); */
                text-transform: uppercase;
                text-align: center;
                color: var(--header-text);
                font-size: 0.9rem;
                cursor: pointer;
                transition: all 0.2s ease-in-out;
                background-color: rgba(0, 190, 243, 0.486);
                border-radius: 0.25rem;
                font-weight: bold;
            }

            button:hover {
                background-color: var(--main);
                color: var(--color-background);
            }

            input:-webkit-autofill,
            input:-webkit-autofill:hover,
            input:-webkit-autofill:focus,
            input:-webkit-autofill:active {
                transition: background-color 5000s ease-in-out 0s;
                -webkit-text-fill-color: var(--header-text);
                -webkit-font-feature-settings: inherit;
            }
        }
    }
</style>