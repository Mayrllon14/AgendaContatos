# Agenda de Contatos - V.0.3.0

Uma aplicação de console em **Java** desenvolvida pedagogicamente para o ensino de estruturas de dados e coleções. A **V.0.3.0** completa o ciclo **CRUD** (Create, Read, Update, Delete) com a introdução da operação de **atualização/alteração** de dados usando `List` e `ArrayList`.

---

## 📌 Sobre o Projeto

A **Agenda de Contatos** é um projeto didático concebido para evoluir gradualmente conforme os conceitos de programação Orientada a Objetos e Estruturas de Dados são apresentados em sala de aula.

### 📈 Evolução do Projeto

| Versão | Armazenamento | Conceitos Aprendidos | Evolução / Limitação |
| :--- | :--- | :--- | :--- |
| **V.0.0.0** | Variáveis simples | `String`, `Scanner`, `if-else`, `switch-case`, repetição | Apenas 1 contato por vez; novo cadastro sobrescreve o anterior. |
| **V.0.1.0** | Arrays (Vetores) | Vetores, índices, tamanho fixo, percurso com `for` | Permite múltiplos contatos, porém com capacidade limitada/fixa. |
| **V.0.2.0** | `List` + `ArrayList` | Coleções, tamanho dinâmico, `add()`, `get()`, `remove()`, `size()` | Vários contatos sem necessidade de pré-definir a capacidade. |
| **V.0.3.0** | `List` + `ArrayList` | Atualização de elementos de uma coleção com `set()` | **CRUD Completo**: Implementa a funcionalidade **Alterar Contato** (Update). |

---

## 🚀 Novidades da Versão 0.3.0

* **Operação UPDATE (Alterar Contato):** Introdução do método `.set(index, element)` do `ArrayList`.
* **Fluxo de Alteração de Dados:**
  1. Busca do contato pelo nome (`equalsIgnoreCase`).
  2. Mapeamento da posição (índice) nas listas paralelas (`nomes`, `celulares`, `emails`).
  3. Solicitação dos novos dados.
  4. Atualização exata da posição desejada usando `set()`.
  5. Tratamento para contatos não encontrados (`posicao == -1`).
* **CRUD Completo:**
  * **C**reate $
ightarrow$ `add()`
  * **R**ead $
ightarrow$ `get()` / `size()`
  * **U**pdate $
ightarrow$ `set()` *(Novidade da V.0.3.0)*
  * **D**elete $
ightarrow$ `remove()`

---

## 💻 Código-Fonte (`Principal.java`)

```java
package br.edu.principal;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Principal {

    public static void main(String[] args) {
        List<String> nomes = new ArrayList<>();
        List<String> celulares = new ArrayList<>();
        List<String> emails = new ArrayList<>();
        Scanner sc = new Scanner(System.in);
        
        int opcao;
        boolean continuar = true;

        System.out.println("=================================");
        System.out.println("       AGENDA DE CONTATOS        ");
        System.out.println("            V.0.3.0              ");
        System.out.println("=================================");
        System.out.println("Bem-vindo!");

        while (continuar) {
            System.out.println();
            System.out.println("1 - Adicionar contato");
            System.out.println("2 - Listar contatos");
            System.out.println("3 - Procurar contato");
            System.out.println("4 - Alterar contato");
            System.out.println("5 - Excluir contato");
            System.out.println("6 - Sair");
            System.out.print("Escolha uma opção: ");
            opcao = sc.nextInt();
            sc.nextLine(); // Limpar buffer

            switch (opcao) {
                case 1 -> {
                    System.out.println("=== ADICIONAR CONTATO ===");
                    System.out.print("Digite o nome: ");
                    String nome = sc.nextLine();
                    System.out.print("Digite o celular: ");
                    String celular = sc.nextLine();
                    System.out.print("Digite o email: ");
                    String email = sc.nextLine();

                    nomes.add(nome);
                    celulares.add(celular);
                    emails.add(email);
                    System.out.println("Contato adicionado com sucesso!");
                }
                case 2 -> {
                    System.out.println("=== LISTAR CONTATOS ===");
                    if (nomes.isEmpty()) {
                        System.out.println("Nenhum contato cadastrado!");
                    } else {
                        for (int i = 0; i < nomes.size(); i++) {
                            System.out.println("--------------------");
                            System.out.println("Nome: " + nomes.get(i));
                            System.out.println("Celular: " + celulares.get(i));
                            System.out.println("Email: " + emails.get(i));
                        }
                    }
                }
                case 3 -> {
                    System.out.println("=== PROCURAR CONTATO ===");
                    System.out.print("Digite o nome do contato: ");
                    String nomeBusca = sc.nextLine();
                    boolean encontrado = false;

                    for (int i = 0; i < nomes.size(); i++) {
                        if (nomes.get(i).equalsIgnoreCase(nomeBusca)) {
                            System.out.println("--------------------");
                            System.out.println("Nome: " + nomes.get(i));
                            System.out.println("Celular: " + celulares.get(i));
                            System.out.println("Email: " + emails.get(i));
                            encontrado = true;
                        }
                    }

                    if (!encontrado) {
                        System.out.println("Contato não encontrado!");
                    }
                }
                case 4 -> {
                    System.out.println("=== ALTERAR CONTATO ===");
                    System.out.print("Digite o nome do contato: ");
                    String nomeProcurado = sc.nextLine();
                    int posicao = -1;

                    for (int i = 0; i < nomes.size(); i++) {
                        if (nomes.get(i).equalsIgnoreCase(nomeProcurado)) {
                            posicao = i;
                            break;
                        }
                    }

                    if (posicao != -1) {
                        System.out.print("Digite o novo nome: ");
                        String novoNome = sc.nextLine();
                        System.out.print("Digite o novo celular: ");
                        String novoCelular = sc.nextLine();
                        System.out.print("Digite o novo email: ");
                        String novoEmail = sc.nextLine();

                        nomes.set(posicao, novoNome);
                        celulares.set(posicao, novoCelular);
                        emails.set(posicao, novoEmail);

                        System.out.println("Contato alterado com sucesso!");
                    } else {
                        System.out.println("Contato não encontrado!");
                    }
                }
                case 5 -> {
                    System.out.println("=== EXCLUIR CONTATO ===");
                    System.out.print("Digite o nome do contato: ");
                    String nomeExcluir = sc.nextLine();
                    boolean excluido = false;

                    for (int i = 0; i < nomes.size(); i++) {
                        if (nomes.get(i).equalsIgnoreCase(nomeExcluir)) {
                            nomes.remove(i);
                            celulares.remove(i);
                            emails.remove(i);
                            excluido = true;
                            System.out.println("Contato excluído com sucesso!");
                            break;
                        }
                    }

                    if (!excluido) {
                        System.out.println("Contato não encontrado!");
                    }
                }
                case 6 -> {
                    System.out.println("Saindo da Agenda de Contatos...");
                    continuar = false;
                }
                default -> System.out.println("Opção inválida!");
            }
        }
        sc.close();
    }
}
```

---

## 🛠️ Como Executar

1. **Pré-requisitos:** Ter o Java Development Kit (JDK 17+) instalado.
2. **Compilação:**
   ```bash
   javac br/edu/principal/Principal.java
   ```
3. **Execução:**
   ```bash
   java br.edu.principal.Principal
   ```

---

## 🛠️ Resumo dos Métodos Utilizados (`java.util.List`)

| Método | Finalidade no Projeto | Operação CRUD |
| :--- | :--- | :--- |
| `add(e)` | Adiciona um novo elemento ao final da lista | **Create** |
| `get(i)` | Obtém o elemento presente no índice `i` | **Read** |
| `set(i, e)` | Substitui o elemento no índice `i` pelo novo valor `e` | **Update** |
| `remove(i)` | Remove o elemento presente no índice `i` | **Delete** |
| `size()` | Retorna o total de elementos cadastrados | Auxiliar de Consulta |
