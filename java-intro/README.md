# Introdução à Java

## Sintaxe Básica:

- Declaração de Classes
    
    ```java
    public class MinhaClasse {
        // Conteúdo da classe
    }
    ```
    
    - A palavra-chave **`public`** indica que a classe pode ser acessada de qualquer lugar.
    - O nome da classe (**`MinhaClasse`** neste exemplo) deve começar com uma letra maiúscula.
    - O conteúdo da classe, que pode incluir variáveis, métodos e construtores, é definido entre chaves **`{}`**.
- Declaração de Métodos
    
    ```java
    public void meuMetodo() {
        // Conteúdo do método
    }
    ```
    
    - A palavra-chave **`public`** indica que o método pode ser acessado de qualquer lugar.
    - **`void`** é o tipo de retorno, que significa que o método não retorna nenhum valor.
    - O nome do método (**`meuMetodo`** neste exemplo) segue convenções de nomenclatura de começar com letra minúscula e usar a notação CamelCase.
    - Os parâmetros do método, se houver algum, seriam listados entre parênteses.
- Declaração de Variáveis
    - Tipos de variáveis em Java variam em tamanho de armazenamento, propósito e faixa de valores.
        1. Tipos primitivos são para valores simples: números, caracteres e lógica (true/false).
        2. Tipos de referência não armazenam diretamente o valor real dos dados, mas sim referenciam onde os dados estão armazenados na memória que apontam para objetos mais complexos, como instâncias de classes, strings e arrays.
        3. Tipos wrapper encapsulam primitivos, permitindo seu uso como objetos.
    
    ```java
    // Tipos Primitivos: 
    int idade; 
    double salario = 1000.50; 
    boolean m = true;
    
    // Tipos de Referência:
    String nome = "Alice"; 
    int[] numeros = new int[5]; // array de tipo primitivo
    String[] nomes = new String[]{"Quelita", "Thiago"}; // array de tipo de referencia
    int[][] matriz; // array de arrays (matrizes)
    ```
    
    - O tipo de variável (como **`int`**, **`double`**, **`String`**) indica o tipo de dado que a variável pode armazenar.
    - O nome da variável segue convenções de nomenclatura, como começar com letra minúscula e usar a notação CamelCase.
    - Você pode declarar variáveis sem inicializá-las, mas é uma boa prática sempre inicializá-las antes de usá-las.
- Modificadores de Acesso
    
    Modificadores de acesso controlam a visibilidade dos métodos, classes e variáveis.
    
    - `public` : permite acesso irrestrito
    - `private` : restringe o acesso apenas à própria classe; acesso mais restritivo para encapsular detalhes internos
    - `protected` : visibilidade na própria classe, em subclasses (herdeiras) e em classes dentro do mesmo pacote (package)
    - `package-private` : permite que todas as classes no mesmo pacote acessem o membro, mas o oculta de classes fora do pacote, mesmo que sejam subclasses