# Agenda de Contatos — V.0.1.0

> Roteiro de Desenvolvimento Incremental para a disciplina de **Programação Orientada a Objetos (POO)**  
> **Professor:** Dr. Róger Moura Sarmento  
> **Instituição:** Instituto Federal de Educação, Ciência e Tecnologia do Ceará (IFCE) — Campus Maranguape  

---

## 📌 Sobre esta Versão (V.0.1.0)

A versão **V.0.1.0** representa o primeiro passo da evolução incremental no armazenamento de dados do projeto **Agenda de Contatos**. 

Na versão anterior (`V.0.0.0`), a aplicação utilizava variáveis simples (`String`), o que limitava a agenda a guardar apenas **1 contato por vez** (um novo cadastro sobrescrevia o anterior). Nesta versão `V.0.1.0`, introduzimos o uso de **Arrays (Vetores)**, permitindo armazenar múltiplos contatos na memória, porém com uma **capacidade máxima fixa**.

> 💡 **Nota Didática:** Esta versão foca no domínio de estruturas de dados estáticas (Arrays), manipulação de índices e laços de repetição, antes de avançarmos para coleções dinâmicas (`List`/`ArrayList` na V.0.2.0) e Orientação a Objetos.

---

## 🚀 Conceitos Trabalhados

- **Declaração e Instanciação de Arrays:** Uso da sintaxe `String[]` e alocação de memória com `new String[capacidade]`.
- **Índices de Arrays:** Compreensão do acesso indexado base de `0` a `N-1`.
- **Capacidade Fixa vs. Contagem de Elementos:** Diferença prática entre o tamanho total alocado (`array.length`) e a quantidade real de elementos cadastrados (`quantidade`).
- **Navegação com Laços (`for`):** Percurso de vetores para exibição e busca de dados.
- **Relacionamento por Índice:** Manutenção da consistência dos dados de um contato correlacionando o mesmo índice em múltiplos arrays (`nomes[i]`, `celulares[i]`, `emails[i]`).
- **Reorganização Manual em Exclusões:** Deslocamento de elementos para a esquerda (*shift*) ao remover um registro para não deixar posições nulas intermediárias (*"buracos"*).
- **Tratamento de Limites:** Validação de estouro da capacidade máxima do array (`ArrayIndexOutOfBoundsException`).

---

## 🗺️ Mapa de Evolução das Versões

| Versão | Armazenamento | Conceitos / Aprendizado | Limitações / Motivação |
| :--- | :--- | :--- | :--- |
| **V.0.0.0** | Variáveis simples | `String`, `Scanner`, `if-else`, `switch-case`, `while` | Armazena apenas **1 contato**; sobrescreve ao reescrever. |
| **V.0.1.0** *(Atual)* | **Arrays (Vetores)** | **Declaração de vetores, índices, laço `for`, `capacidade`, controle de limites** | **Permite vários contatos, mas exige capacidade fixa (ex: 5).** |
| **V.0.2.0** *(Próxima)* | `List` / `ArrayList` | Coleções dinâmicas, `add()`, `get()`, `remove()`, `size()` | Elimina a limitação de tamanho fixo. |

---

## 🛠️ O que mudou no Código?

### 1. Declaração do Armazenamento
- **Antes (V.0.0.0):**
  ```java
  String nome = "";
  String celular = "";
  String email = "";
