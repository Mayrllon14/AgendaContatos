# Agenda de Contatos — V.0.0.0

> **Material Didático de Programação Orientada a Objetos (POO)**  
> **Professor:** Dr. Róger Moura Sarmento  
> **Instituição:** Instituto Federal de Educação, Ciência e Tecnologia do Ceará (IFCE) — Campus Maranguape  
> **Data:** 23 de agosto de 2026  

---

## 📌 Sobre o Projeto

Este repositório contém a versão **V.0.0.0** do projeto **Agenda de Contatos**, desenvolvido como material de apoio pedagógico para a disciplina de **Programação Orientada a Objetos (POO)**. 

O projeto adota uma abordagem de **desenvolvimento incremental**, partindo de um programa básico em Java e introduzindo gradualmente novos conceitos, estruturas de controle e paradigmas de programação a cada versão.

---

## 🎯 Objetivos da Versão V.0.0.0

Nesta primeira versão procedural e estruturada, o foco é estabelecer a estrutura fundamental de um programa em Java e praticar lógica de programação básica:

- Compreender o ponto de entrada (`public static void main`).
- Manipular dados utilizando variáveis do tipo `String`.
- Realizar entrada e saída de dados via terminal com `Scanner` e `System.out`.
- Implementar controle de fluxo com `switch-case` e tomada de decisão com `if-else`.
- Criar um ciclo de repetição contínuo para a aplicação usando `while`.

---

## ⚠️ Limitações da Versão V.0.0.0

Por ser a versão inicial do projeto:
- **Armazenamento Único:** A agenda consegue armazenar **apenas um (1) contato** por vez (`nome`, `celular` e `email`).
- **Sobrescrita de Dados:** Ao cadastrar um novo contato, os dados do contato anterior são substituídos.
- **Estrutura Procedural:** Todo o sistema é construído dentro da classe `Principal` e unicamente no método `main()`, sem a criação de classes de domínio (como `Contato`) ou arrays/coleções.

*Nota: Estas limitações são intencionais e pedagógicas, visando motivar a necessidade de introdução de arrays na versão V.0.1.0.*

---

## 🗺️ Etapas de Desenvolvimento (Roteiro Incremental)

1. **Etapa 1:** Estrutura inicial do programa Java (`main` e exibição de boas-vindas).
2. **Etapa 2:** Declaração das variáveis (`nome`, `celular`, `email`) para armazenar o contato.
3. **Etapa 3:** Construção e exibição do menu de opções no console.
4. **Etapa 4:** Leitura da opção informada pelo usuário com `Scanner`.
5. **Etapa 5:** Controle de fluxo do menu utilizando a estrutura `switch-case`.
6. **Etapa 6:** Implementação da funcionalidade **Adicionar Contato**.
7. **Etapa 7:** Estrutura de repetição `while` para manter a aplicação em execução.
8. **Etapa 8:** Implementação das funcionalidades de **Listar**, **Procurar** e **Excluir** o contato.
9. **Etapa 9:** Testes de fluxo, validação com `isEmpty()` e `equalsIgnoreCase()`, e finalização da versão.

---

## 🖥️ Funcionalidades do Menu
