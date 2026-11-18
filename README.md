# Histórico de Projetos - Aulas de Java

Repositório destinado ao armazenamento e versionamento das atividades e códigos desenvolvidos nas aulas de Java (período de 28/07 a 19/08).

## 📂 Estrutura do Repositório

### 1. Aula 1 (29/07 e 31/07) - Introdução a Orientação a Objetos
* **`Carro.java`**: Classe base contendo atributos e métodos de aceleração, redução e buzina[cite: 1].
* package aula1;

public class Carro {
    // Atributos[cite: 1]
    String nome;
    String marca;
    int ano;
    int vel;

    // Métodos[cite: 1]
    void acelerar(int aceleracao) {
        vel += aceleracao;
    }

    void reduzir(int reduzir) {
        vel -= reduzir;
    }

    void buzinar() {
        System.out.println("bibibi");
    }
}
* **`TesteCarro.java`**: Classe de teste para instanciar o objeto e manipular suas propriedades[cite: 1, 2].
package aula1;

public class TesteCarro {
    public static void main(String[] args) {
        Carro c1 = new Carro();

        c1.nome = "Ferrari";
        c1.marca = "Fiat";
        c1.ano = 2026;
        c1.vel = 60;

        c1.acelerar(10);
        System.out.println("Velocidade: " + c1.vel + " km/h");
        
        c1.reduzir(30);
        System.out.println("Velocidade: " + c1.vel + " km/h");
    }
}


### 2. Aula 2 (05/08) - Sobrecarga de Construtores
* **`Produto.java`**: Exemplo prático de criação de múltiplos construtores na mesma classe[cite: 2].
* package exercicios;

public class Produto {
    String modelo;
    float ano;

    Produto() {
    }

    Produto(String modelo) {
        this.modelo = modelo;
    }

    Produto(String modelo, float ano) {
        this.modelo = modelo;
        this.ano = ano; // Correção da atribuição ausente no original[cite: 2]
    }
}
* **`TestarCarro.java`**: Classe executável que testa as diferentes formas de inicializar os objetos[cite: 3].
* package exercicios;

public class TestarCarro {
    public static void main(String[] args) {
        Produto p1 = new Produto();
        p1.modelo = "Uno com Escada";
        p1.ano = 2013;

        Produto p2 = new Produto("Ferrari");
        p2.ano = 2020;

        Produto p3 = new Produto("Gol", 2016);

        System.out.println("Modelo: " + p1.modelo + " / Ano: " + p1.ano);
        System.out.println("Modelo: " + p2.modelo + " / Ano: " + p2.ano);
        System.out.println("Modelo: " + p3.modelo + " / Ano: " + p3.ano);
    }
}

### 3. Aula 3 (12/08) - Construtores e Atributos Avançados
* **`Produto.java`**: Estrutura robusta de produto com múltiplos parâmetros (nome, marca e valor)[cite: 3].
* package programacao_algoritimo;

public class Produto {
    // Atributos[cite: 3]
    String nome;
    String marca;
    Float valor;

    // Construtores[cite: 3]
    Produto() {
    }

    Produto(String nome) {
        this.nome = nome; // Correção da atribuição[cite: 3]
    }

    Produto(String nome, String marca) {
        this.nome = nome;
        this.marca = marca;
    }

    Produto(String nome, String marca, Float valor) {
        this.nome = nome; // Correção da atribuição[cite: 3]
        this.marca = marca;
        this.valor = valor;
    }
}
* **`ProdutoTestar.java`**: Validação e exibição dos dados utilizando os construtores criados[cite: 4].
* package programacao_algoritimo;

public class ProdutoTestar {
    public static void main(String[] args) {
        // Construtor padrão[cite: 4]
        Produto p1 = new Produto();
        p1.nome = "Caneta Preta";
        p1.marca = "Bic";
        p1.valor = 1.50f;

        // Construtor de dois parâmetros[cite: 4]
        Produto p2 = new Produto("Caneta Faber");
        p2.valor = 1.67f;

        // Construtor com três parâmetros[cite: 4]
        Produto p3 = new Produto("Borracha", "Mercur", 1.86f);

        // Exibição dos objetos[cite: 4]
        System.out.println("Nome: " + p1.nome + " / Marca: " + p1.marca + " / Valor: " + p1.valor);
        System.out.println("Nome: " + p2.nome + " / Marca: " + p2.marca + " / Valor: " + p2.valor);
        System.out.println("Nome: " + p3.nome + " / Marca: " + p3.marca + " / Valor: " + p3.valor);
    }
}

### 4. Aula 4 (19/08) - Encapsulamento
* **`Aluno.java`**: Implementação de atributos privados (`private`) e uso de métodos `getters` e `setters` com validação de dados[cite: 4, 5].
* package exemplo3;

public class Aluno {
    private String nome;
    private int idade;

    public void setNome(String nome) {
        this.nome = nome; // Correção da atribuição[cite: 4]
    }

    public String getNome() {
        return nome;
    }

    public void setIdade(int idade) {
        if (idade > 0 && idade < 130) {
            this.idade = idade; // Correção da atribuição[cite: 4]
            System.out.println("Idade cadastrada com sucesso!");
        } else {
            System.out.println("Erro: Idade inválida");
        }
    }
}
* **`AlunoTestar.java`**: Execução e teste das regras de segurança e encapsulamento aplicadas ao objeto `Aluno`[cite: 5].
* package exemplo3;

public class AlunoTestar {
    public static void main(String[] args) {
        // Instanciar classe Aluno[cite: 5]
        Aluno aluno1 = new Aluno();
        
        aluno1.setNome("Helio");
        System.out.println(aluno1.getNome());
        
        aluno1.setIdade(15);
    }
}

---
*Desenvolvido por Pedro Hanry Coutinho Oliveira (1 DS).*
