# Introdução à Orientação a Objetos (OO): Princípios da programação orientada a objetos

## Classes: Criação de classes

>Classe são modelos para criar objetos. Elas descrevem as propriedades e comportamentos que os objetos terão.
  1. **Classe Padrão (Default Class):** sem especificação de um modificador de Acesso (public, privated, protected), ela terá acesso de pacote o que significa dizer que só pode ser acessada por outras classes do mesmo pacote.
        ```java
          class MinhaClasse {
              // Definição da classe aqui
          }
        ```
    
  2. **Classe Pública (Public Class):** a classe pode ser acessada de qualquer lugar, seja no mesmo pacote ou em pacotes diferentes.
        ```java
        public class MinhaClasse {
            // Definição da classe aqui
        }
        ```
    
  3. **Classe Abstrata (Abstract Class):** Uma classe abstrata é uma classe que não pode ser instanciada diretamente. Ela é usada como um modelo para outras classes (classes filhas) e pode conter métodos abstratos, que devem ser implementados pelas subclasses.
    
        ```java
        public abstract class MinhaClasse {
            // Definição da classe aqui
        }
        ```
    
  4. **Classe Aninhada (Nested Class):** Você pode criar classes dentro de outras classes. Essas são conhecidas como classes aninhadas ou classes internas. Elas podem ser estáticas (pertencentes à classe externa) ou não estáticas (pertencentes a instâncias da classe externa).
    
        ```java
        public class ClasseExterna {
            static class ClasseAninhada {
                // Definição da classe aninhada aqui
            }
        }
        ```
    
  5. **Classe Final (Final Class):** Uma classe final é aquela que não pode ser estendida (ou seja, não pode ter subclasses). Isso é útil quando você deseja que outras classes estendam ou herdem seus membros ou comportamentos.
    
        ```java
        public final class MinhaClasse {
            // Definição da classe aqui
        }
        ```
    
   6. **Classe Enum (Enum Class):** Uma classe enum é usada para definir um conjunto fixo de valores constantes (elementos enum) que representam valores discretos. Os elementos enum são únicos e imutáveis, mas você pode criar novas instâncias da enumeração, desde que sejam subtipos das constantes definidas na enumeração.

        ```java
        public enum DiasDaSemana {
            SEGUNDA, TERÇA, QUARTA, QUINTA, SEXTA, SÁBADO, DOMINGO
        }
        ```

## Objetos: instância de objetos

>Objetos são criados com base no modelo definido pela classe, chamadas de instâncias.

Etapas para instânciar um objeto:
    - Definir uma classe que descreva os atributos e métodos do objeto;
    - Criar um objeto usando a palavra-chave `new`, seguida do construtor da classe, e pode acessar os membros do objeto usando o operador de ponto.
    
```java
  public class Pessoa {
      String nome;
      int idade;
  
      public void apresentar() {
          System.out.println("Olá, meu nome é " + nome + " e tenho " + idade + " anos.");
      }
  }
  
  public class Main {
      public static void main(String[] args) {
          Pessoa pessoa1 = new Pessoa(); // Criar uma instância da classe Pessoa
          pessoa1.nome = "Alice";
          pessoa1.idade = 30;
          pessoa1.apresentar(); // Chama o método apresentar
  
          Pessoa pessoa2 = new Pessoa(); // Criar outra instância da classe Pessoa
          pessoa2.nome = "Bob";
          pessoa2.idade = 25;
          pessoa2.apresentar();
      }
  }
  ```

## Métodos: Definição de métodos

>Métodos são funções que permitem que os objetos realizem ações e interajam com outros objetos.

Etapas para instânciar um objeto:

  - Dentro de uma classe, especifique ou não um modificador de acesso para determinar a visibilidade e a acessibilidade do método (public, privated, protected ou nenhum modificador (padrão ou package-private));
  - Especifique o tipo de retorno do método;
  - Determine o nome do método;
  - Defina os parâmetros (Opcional).

      ```java
        // pode ser iniciado com um modificador de acesso + tipo de retorno + nome + parâmetros
        public void meuMetodo() {
          // lógica do método
        }
    
        // ou pode iniciar diretamente com o tipo de retorno + nome do método + parâmetros
        void novoMetodo(){
          // lógica do método
        }
      ```

## Atributos: atributos em classes

>Atributos são as caracteristicas de um objeto, que também podem ser chamados de variáveis.

Como foi visto na [seção anterior](../java-intro) de Introdução a Java.
    
## Modificadores de Acesso: Public, Private, Protected, Package-private

> Definem a visibilidade e acessibilidade de classes, métodos, variáveis e outros elementos dentro do código.

1. **Public**: torna o elemento acessível de qualquer lugar.
2. **Private**: restrige o acesso apenas para a classe que o contém.
3. **Protected**: restinge o acesso para dentro da classe que o contém, em classes do mesmo pacote e em classes herdeiras (subclasses) mesmo que estejam em pacotes diferentes.
4. **Default (package-private)**: restringe o acesso por classes do mesmo pacote.

        ```java
        public class MinhaClasse {
            public int variavelPublica;
            private int variavelPrivada;
            protected int variavelProtegida;
            int variavelDefault; // Nenhum modificador (default)
        
            public void metodoPublico() {
                // Código acessível de qualquer lugar
            }
        
            private void metodoPrivado() {
                // Código acessível apenas dentro desta classe
            }
        
            protected void metodoProtegido() {
                // Código acessível na mesma classe e em subclasses
            }
        
            void metodoDefault() {
                // Código acessível apenas dentro do mesmo pacote
            }
        }
        ```

## Construtores: Construtores padrão e personalizados

>Um construtor é um método especial que é invocado quando um objeto de uma classe é criado. O construtor tem o mesmo nome da classe e não possui um tipo de retorno explícito. Sua principal finalidade é inicializar os atributos (variáveis de instância) de um objeto quando ele é instanciado.

Características importantes dos construtores em Java:
    - **Nome:** O construtor tem o mesmo nome da classe e pode ter parâmetros. A assinatura do construtor é determinada pela lista de parâmetros, ou seja, a quantidade e os tipos de parâmetros;
    - **Construtor Padrão:** é fornecido inicialmente sem parâmetros e com atributos com valores padrão, como 0 para inteiros, null para objetos e assim por diante;
    - **Construtores Personalizados:** são definidos por meio dos construtires personalizados com parâmetros para inicializar os atributos, que é o que diferencia de outros construtores.

  ```java
  public class Pessoa {
      private String nome;
      private int idade;
  
      // Construtor padrão (sem parâmetros)
      public Pessoa() {
          nome = "Sem nome";
          idade = 0;
      }
  
      // Construtor personalizado
      public Pessoa(String nome, int idade) {
          this.nome = nome;
          this.idade = idade;
      }
  
      // Outros métodos da classe...
  }
```
