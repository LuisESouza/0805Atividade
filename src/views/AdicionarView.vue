<script setup>
    import router from '@/router';
    import { ref } from 'vue';

    const nome = ref("");
    const cpf = ref("");
    const email = ref("");

    const onSubmit = () => {
        const pessoa = {
            nome: nome.value,
            cpf: cpf.value,
            email: email.value
        };

        let pessoas = JSON.parse(localStorage.getItem("pessoas")) || [];
        pessoas.push(pessoa);
        localStorage.setItem("pessoas", JSON.stringify(pessoas));

        router.push("/");
    }
</script>


<template>
    <form @submit.prevent="onSubmit">
        <div>
            <label for="nome">Nome</label>
            <input type="text" id="nome" v-model="nome">
        </div>

        <div>
            <label for="cpf">CPF</label>
            <input type="text" id="cpf" v-model="cpf">
        </div>

        <div>
            <label for="email">E-mail</label>
            <input type="text" id="email" v-model="email">
        </div>

        <button>Salvar</button>
    </form>
</template>