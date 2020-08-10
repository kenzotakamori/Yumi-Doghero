<template>
    <section id="app-contact">
        <h1>Contact</h1>
        <div class="container">
            <form>
                <p>
                    <label for="name">Nome</label>
                    <input v-model="name" type="text" name="name" placeholder="Coloque seu nome">
                </p>
                <p>
                    <label for="email">Email</label>
                    <input v-model="email" type="email" name="email" placeholder="Coloque seu email">
                </p>
                <p>
                    <label for="contactReason">Motivo</label>
                    <select v-model="contactReason" name="contactReason">
                        <option>Dúvida</option>
                        <option>Reserva</option>
                        <option>Outro</option>
                    </select>
                </p>
                <p class="message">
                    <label for="message">Mensagem</label>
                    <input v-model="message" name="message" placeholder="Fala pra gente!">
                </p>
                <div style="width=100%">
                    <input type="submit" value="Enviar!">
                </div>
            </form>
        </div>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                name: null,
                email: null,
                contactReason: null,
                message: null
            }
        },
        methods: {

        }
    }
</script>
<style>
    #app-contact .container {
        min-height: 65vh;
        padding-top: 0;
    }

    form {
        width: 90%;
    }

    form p {
        height: 40px;
        line-height: 40px;
        display: grid;
        grid-gap: 1rem;
        grid-template-columns: minmax(100px, 20%) 1fr;
    }

    form p.message {
        height: 80px;
    }

    form p label {
        font-weight: 700;
        text-align: right;
    }

    form input, form p select {
        padding: 10px;
        font-weight: 700;
    }

    form p select option {
        padding: 10px;
        font-weight: 700;
        line-height: 30px;
    }
</style>