# Agenda de Contatos - V.0.2.0 📇


## 📌 Sobre o Projeto

O **Agenda de Contatos** é um projeto didático desenvolvido de forma incremental para o ensino de Programação Orientada a Objetos. A cada nova versão, novos conceitos de programação são introduzidos e aplicados sobre a versão anterior, permitindo visualizar a evolução do código e compreender a necessidade de novas estruturas e técnicas.

Nesta **Versão 0.2.0 (V.0.2.0)**, o foco central é a transição de **Arrays estáticos (tamanho fixo)** para **Coleções Dinâmicas** com `List` e `ArrayList` da biblioteca padrão do Java (`java.util`).

---

## 🚀 Evolução Incremental do Projeto

| Versão | Armazenamento | Conceitos Trabalhados | Limitações / Motivação |
| :--- | :--- | :--- | :--- |
| **V.0.0.0** | Variáveis Simples | `String`, `Scanner`, `if-else`, `switch-case`, `while` | Armazena apenas **1 contato**. Um novo cadastro sobrescreve o anterior. |
| **V.0.1.0** | Arrays (`String[]`) | Vetores, índices, tamanho fixo, percurso com `for` | Permite múltiplos contatos, mas requer capacidade pré-definida e gerenciamento manual de índices/remoção. |
| **V.0.2.0** <br>*(Atual)* | `List` / `ArrayList` | Coleções dinâmicas, `add()`, `get()`, `remove()`, `size()`, `java.util.*` | Armazena múltiplos contatos com **tamanho dinâmico**. Elimina a necessidade de controle de capacidade e reorganização manual. |

---

## 🎯 Objetivos de Aprendizagem da V.0.2.0

* **Coleções Genéricas (`List<E>` e `ArrayList<E>`):** Compreender a diferença entre a declaração da interface e a instanciação da classe concreta.
* **Tamanho Dinâmico:** Eliminar limites rígidos de capacidade e variáveis de controle manual (como `capacidade` e `cont`).
* **Manipulação de Listas:**
  * `add(elemento)`: Inserir elementos dinamicamente ao final da lista.
  * `get(indice)`: Acessar elementos por seu índice posicional.
  * `remove(indice)`: Remover elementos diretamente sem a necessidade de deslocar manualmente os itens restantes.
  * `size()`: Consultar a quantidade atual de elementos na lista.

---

## 💻 Código Fonte (`Principal.java`)

```java
package br.edu.principal;

import java.util.Scanner;
import java.util.List;
import java.util.ArrayList;

public class Principal {

    public static void main(String[] args) {
        // Declaração e instanciação de coleções dinâmicas
        List<String> nomes = new ArrayList<>();
        List<String> celulares = new ArrayList<>();
        List<String> emails = new ArrayList<>();

        Scanner sc = new Scanner(System.in);
        int opcao;
        boolean continuar = true;

        System.out.println("==========================");
        System.out.println("    AGENDA DE CONTATOS    ");
        System.out.println("         V.0.2.0          ");
        System.out.println("==========================");
        System.out.println("Bem-vindo!");

        while (continuar) {
            System.out.println();
            System.out.println("1 - Adicionar contato");
            System.out.println("2 - Listar contatos");
            System.out.println("3 - Procurar contato");
            System.out.println("4 - Excluir contato");
            System.out.println("5 - Sair");
            System.out.println();
            System.out.print("Escolha uma opção: ");

            opcao = sc.nextInt();
            sc.nextLine(); // Limpeza de buffer

            switch (opcao) {
                case 1 -> {
                    System.out.println("\n--- ADICIONAR CONTATO ---");
                    System.out.print("Nome: ");
                    nomes.add(sc.nextLine());

                    System.out.print("Celular: ");
                    celulares.add(sc.nextLine());

                    System.out.print("E-mail: ");
                    emails.add(sc.nextLine());

                    System.out.println("Contato salvo com sucesso!");
                }
                case 2 -> {
                    System.out.println("\n--- LISTAR CONTATOS ---");
                    if (nomes.size() == 0) {
                        System.out.println("Nenhum contato encontrado!");
                    } else {
                        for (int i = 0; i < nomes.size(); i++) {
                            System.out.println("\nContato " + (i + 1));
                            System.out.println("Nome: " + nomes.get(i));
                            System.out.println("Celular: " + celulares.get(i));
                            System.out.println("E-mail: " + emails.get(i));
                        }
                    }
                }
                case 3 -> {
                    System.out.println("\n--- PROCURAR CONTATO ---");
                    System.out.print("Digite o nome que deseja procurar: ");
                    String nomeBusca = sc.nextLine();
                    boolean encontrado = false;

                    for (int i = 0; i < nomes.size(); i++) {
                        if (nomes.get(i).equalsIgnoreCase(nomeBusca)) {
                            System.out.println("\nContato encontrado!");
                            System.out.println("Nome: " + nomes.get(i));
                            System.out.println("Celular: " + celulares.get(i));
                            System.out.println("E-mail: " + emails.get(i));
                            encontrado = true;
                        }
                    }

                    if (!encontrado) {
                        System.out.println("Contato não encontrado.");
                    }
                }
                case 4 -> {
                    System.out.println("\n--- EXCLUIR CONTATO ---");
                    if (nomes.size() == 0) {
                        System.out.println("Nenhum contato cadastrado.");
                    } else {
                        System.out.print("Digite o nome do contato que deseja excluir: ");
                        String nomeExcluir = sc.nextLine();
                        int indiceExcluir = -1;

                        for (int i = 0; i < nomes.size(); i++) {
                            if (nomes.get(i).equalsIgnoreCase(nomeExcluir)) {
                                indiceExcluir = i;
                            }
                        }

                        if (indiceExcluir == -1) {
                            System.out.println("Contato não encontrado.");
                        } else {
                            nomes.remove(indiceExcluir);
                            celulares.remove(indiceExcluir);
                            emails.remove(indiceExcluir);
                            System.out.println("Contato excluído com sucesso!");
                        }
                    }
                }
                case 5 -> {
                    System.out.println("Saindo...");
                    continuar = false;
                }
                default -> System.out.println("Opção inválida!");
            }
        }
        sc.close();
    }
}
