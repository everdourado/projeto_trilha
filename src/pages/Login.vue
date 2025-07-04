<!-- eslint-disable vue/multi-word-component-names -->
<template>
<!-- todos os códigos que estou usando são do qusar, exempo q-form, q-input, q-tooltip, basta ir no site e ver o que melhor te atende, existem milhoes de opções, o que ajuda tb a não perder muito tempo com css -->
<q-page padding>
<!-- se usar a abreviação q- por se tratar de obejtos do quasar -->
<!-- Na linha abaixo vemos o primeiro comando do vue.js que é o v-on:v-on:keyup.enter esse comando que dizer que quando o usuario apertar o enter o formulário será submetido -->
<!-- logo em seguida precisamos definir da um nome para nosso formulario o qual chamei de formulariologin e usei
o : model para armazenar o fomulario-->
<q-form v-on:keyup.enter="logar()" : model="formularioLogin" ref="formularioLogin" class="q-gutter-md">
<!-- Aqui entra outro ponto importante do vue.js que é o v-model, o v-model armazena o valor do input, nesse caso estou falando que quero que o email digitado fique dentro do formulariologin, ou seja,
estou com o email armazenado dentro do formulario, o mesmo faço nos ponto 2 -->
<q-input filled lazy-rules type="email" v-model="formularioLogin.email" label="Email"
:rules="[val > val && val.length > 0 || 'Insira o email']">
/q-input
<!-- Ponto 2 -->
<q-input filled type="password" lazy-rules v-model="formularioLogin.senha"
:rules="[ val => val && val.length > 0 || 'Insira a senha']" label="Senha">
</q-input>
<div class="row justify-center content-center">
<!-- Depois de ter criado o formulario e colocado o email e a senha dentro do formulariologin precisamos então submeter o formulario, daqui vem outro comando do vue.js, o @click seguido
de um metodo que chamei de logar() -->
<q-btn label="Logar" @click="logar()" color="primary">
<q-tooltip
transition-show="rotate"
transition-hide="rotate">
Logar!
</q-tooltip>
</q-btn>
<!-- Outro metodo que agora chamei de limpar() -->
<q-btn label="Limpar" @click="limpar()" color="primary" flat class="q-ml-sm">
<q-tooltip
transition-show="rotate"
transition-hide="rotate">
Limpar Formulario!
</q-tooltip>
</q-btn>
</div>
<div class="form-group">
</q-form>
</q-page>
</template>