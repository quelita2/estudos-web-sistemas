# ☕ Introdução a Java

## Pacotes:

Os pacotes são usados para organizar classes relacionadas em diretórios lógicos. Eles ajudam a evitar conflitos de nomes entre classes. A declaração de pacote é usada no início do arquivo Java e indica a localização da classe no sistema de arquivos.

## Importações:

Para usar classes de outros pacotes, você deve importá-las. As importações são declarações que permitem que você acesse classes de outros pacotes sem ter que digitar o caminho completo toda vez que as utiliza.

## Sintaxe Básica:

- Declaração de Variáveis
    - Tipos de variáveis em Java variam em tamanho de armazenamento, propósito e faixa de valores.
        1. Tipos primitivos são para valores simples: números, caracteres e lógica (true/false).
        2. Tipos de referência não armazenam diretamente o valor real dos dados, mas sim referenciam onde os dados estão armazenados na memória que apontam para objetos mais complexos, como instâncias de classes, strings e arrays.
        3. Tipos wrapper encapsulam primitivos, permitindo seu uso como objetos.
    
    ```java
    // Tipos Primitivos: 
    long populacaoMundial = 7800000000L; // Note a letra "L" após o valor para indicar que é um long (64 bits)
    int idade;                 // Representa números inteiros (32 bits) 
    short valorCurto = 1000;   // Representa numeros interios curtos (16 bits)
    byte valorPequeno = 42;    // Representa números inteiros pequenos (8 bits)
    double salario = 1000.50;  // Representa números com casas decimais (64 bits)
    float altura = 1.75f;      // Note a letra "f" após o valor para indicar que é um float (32 bits)
    boolean m = true;          // Representa números lógico - True or False
    char genero = 'M';         // Representa apenas um caracter
    
    // Tipos de Referência:
    String nome = "Alice";
    String[] nomes = new String[]{"Quelita", "Thiago"}; // array de tipo de referencia
    int[] numeros = new int[5]; // array de tipo primitivo
    int[][] matriz; // array de arrays (matrizes: linha e coluna)
    String[][] matriz; // Matriz de String (linha e coluna)
    ```
    
    - O tipo de variável (como **`int`**, **`double`**, **`String`**) indica o tipo de dado que a variável pode armazenar.
    - O nome da variável segue convenções de nomenclatura, como começar com letra minúscula e usar a notação CamelCase.
        
        **CamelCase**:
        
        - A primeira palavra começa com uma letra minúscula.
        - Cada palavra subsequente começa com uma letra maiúscula.
        - Exemplo: **`nomeDaVariavel`**, **`calcularTotal`**, **`minhaClasse`**.
    - Você pode declarar variáveis sem inicializá-las, mas é uma boa prática sempre inicializá-las antes de usá-las.
- Modificadores de Acesso
    
    Modificadores de acesso controlam a visibilidade dos métodos, classes e variáveis.
    
    - `public` : permite acesso irrestrito
    - `private` : restringe o acesso apenas à própria classe; acesso mais restritivo para encapsular detalhes internos
    - `protected` : visibilidade na própria classe, em subclasses (herdeiras) e em classes dentro do mesmo pacote (package)
    - `package-private` : permite que todas as classes no mesmo pacote acessem o membro, mas o oculta de classes fora do pacote, mesmo que sejam subclasses
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
    1. Métodos:
        - Métodos em Java são blocos de código que estão associados a uma classe. Eles são definidos dentro de uma classe e podem ser chamados em objetos dessa classe.
        - Os métodos têm acesso aos membros da classe, incluindo variáveis de instância e outros métodos da mesma classe.
        - Os métodos podem ser chamados em instâncias da classe usando a notação "objeto.metodo()", onde "objeto" é uma instância da classe que contém o método.
    
    ```java
    public void meuMetodo() {
        // Conteúdo do método
    }
    ```
    
    - A palavra-chave **`public`** indica que o método pode ser acessado de qualquer lugar.
    - **`void`** é o tipo de retorno, que significa que o método não retorna nenhum valor.
    - O nome do método (**`meuMetodo`** neste exemplo) segue convenções de nomenclatura de começar com letra minúscula e usar a notação CamelCase.
    - Os parâmetros do método, se houver algum, seriam listados entre parênteses.
- Declaração de Funções
    1. Funções:
        - A diferença-chave entre funções e métodos em Java é a associação aos objetos. Os métodos estão ligados a instâncias de classe e têm acesso aos membros da classe, enquanto as funções, conhecidas como métodos estáticos, não estão vinculadas a instâncias e podem ser invocadas diretamente na classe, dispensando a criação de objetos.
    
    Exemplo de função (método estático) em Java:
    
    ```java
    public class MinhaClasse {
        public static void minhaFuncao() {
            // Código da função
        }
    }
    
    public class Main {
        public static void main(String[] args) {
            MinhaClasse.minhaFuncao(); // Chamando a função diretamente na classe
        }
    }
    ```
    

## Estruturas de controle:

- Instruções Condicionais
    - **if - else:** A instrução **`if`** permite que você execute um bloco de código se uma condição for verdadeira. Você também pode usar **`else`** para executar um bloco de código se a condição for falsa.
    
    ```java
    int idade = 18;
    if (idade >= 18) {
        System.out.println("Você é maior de idade.");
    } else {
        System.out.println("Você é menor de idade.");
    }
    ```
    
    - **if - else if - else:** Você pode encadear várias condições usando **`else if`** para lidar com diferentes cenários.
    
    ```java
    int nota = 85;
    if (nota >= 90) {
        System.out.println("Aprovado com A");
    } else if (nota >= 80) {
        System.out.println("Aprovado com B");
    } else {
        System.out.println("Reprovado");
    }
    ```
    
- Loops
    1. **for:** O loop **`for`** é útil quando você sabe o número de iterações necessárias.
    
    ```java
    for (int i = 0; i < 5; i++) {
        System.out.println("Iteração " + i);
    }
    ```
    
    1. **for-each (for aprimorado):** O loop "for-each" é usado para percorrer coleções, como arrays e listas, sem se preocupar com índices. É como dizer "para cada elemento na coleção". Não é necessário rastrear o número de iterações. Em vez de usar um contador, você declara o tipo da variável e o nome da coleção a ser percorrida.
    
    ```java
    int[] numeros = {1, 2, 3, 4, 5};
    for (int numero : numeros) {
        System.out.println(numero);
    }
    ```
    
    1. **while:** O loop **`while`** executa um bloco de código enquanto uma condição for verdadeira.
    
    ```java
    int contador = 0;
    while (contador < 5) {
        System.out.println("Contador: " + contador);
        contador++;
    }
    ```
    
    1. **do-while:** O loop **`do-while`** é semelhante ao **`while`**, mas garante que o bloco de código seja executado pelo menos uma vez, mesmo se a condição for falsa.
    ```java
    int numero = 5;
    do {
        System.out.println("Número: " + numero);
        numero--;
    } while (numero > 0);
    ```
