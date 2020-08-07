<template>
    <section id="app-contact">
        <h1>Contact</h1>
        <div class="container">
            <form>
                <p>
                    <label for="name">Nome</label>
                    <input v-model="name" type="text" name="name">
                </p>
                <p>
                    <label for="email">Email</label>
                    <input v-model="email" type="email" name="email">
                </p>
                <p>
                    <label for="contactReason">Motivo</label>
                    <select v-model="contactReason" name="contactReason">
                        <option>Dúvida</option>
                        <option>Reserva</option>
                        <option>Outro</option>
                    </select>
                </p>
                <p>
                    <label for="message">Mensagem</label>
                    <input v-model="message" name="message">
                </p>
                <p>
                    <input type="submit" value="Enviar!">
                </p>
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
    form {
        width: 90%;
    }

    form p {
        height: 40px;
        line-height: 40px;
        display: grid;
        grid-gap: 1rem;
        grid-template-columns: minmax(100px, 30%) 1fr;
    }

    form p input[name="message"] {
        height: 120px;
    }

    form p label {
        font-weight: 700;
        text-align: right;
    }
</style>