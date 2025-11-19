# Roteiro de Estudos: Introdução ao JavaScript - Semana 6

## Objetivo da Semana

Dominar o conceito de objetos em JavaScript, aprendendo a criar estruturas de dados complexas que representam entidades do mundo real com propriedades e métodos, preparando-se para programação orientada a objetos e manipulação avançada de dados.

---

## ⚠️ PRÉ-REQUISITOS OBRIGATÓRIOS

**ATENÇÃO:** Antes de iniciar esta semana, você DEVE dominar:

- ✅ Variáveis (`let` e `const`)
- ✅ Tipos de dados primitivos
- ✅ Estruturas condicionais
- ✅ Loops (for, while)
- ✅ Arrays e seus métodos
- ✅ Funções básicas (será útil, mas revisaremos)

**Se ainda tem dúvidas:** Revise as Semanas 1-5 antes de prosseguir!

---

## Parte 1: Introdução aos Objetos

### 1.1: O que são Objetos?

Um **objeto** é uma estrutura de dados que armazena **pares chave-valor**, permitindo representar entidades complexas com suas características (propriedades) e comportamentos (métodos).

**Analogia da vida real:**

```
Pessoa Real:
- Nome: João Silva
- Idade: 28 anos
- Profissão: Desenvolvedor
- Email: joao@email.com
- Ações: Falar, Andar, Trabalhar

Objeto JavaScript:
{
    nome: "João Silva",
    idade: 28,
    profissao: "Desenvolvedor",
    email: "joao@email.com",
    falar: function() { ... }
}
```

**Diferença entre Arrays e Objetos:**

```javascript
// ARRAY - Lista ordenada, acesso por índice
const pessoa = ["João", 28, "Desenvolvedor"];
console.log(pessoa[0]); // "João" - mas o que é [0]?

// OBJETO - Dados nomeados, acesso por chave
const pessoa = {
  nome: "João",
  idade: 28,
  profissao: "Desenvolvedor",
};
console.log(pessoa.nome); // "João" - muito mais claro!
```

### 1.2: Criando Objetos

```javascript
// Método 1: Notação Literal {} (RECOMENDADO)
const pessoa = {
  nome: "Maria",
  idade: 25,
  cidade: "São Paulo",
};

// Método 2: Construtor Object() (menos comum)
const carro = new Object();
carro.marca = "Toyota";
carro.modelo = "Corolla";
carro.ano = 2023;

// Objeto vazio
const vazio = {};

// Objeto com diferentes tipos de valores
const produto = {
  id: 1,
  nome: "Notebook",
  preco: 2500.0,
  emEstoque: true,
  categorias: ["Eletrônicos", "Informática"],
  especificacoes: {
    processador: "Intel i7",
    memoria: "16GB",
  },
};
```

### 1.3: Propriedades de Objetos

**Propriedades** são as características do objeto (pares chave-valor).

```javascript
const livro = {
  titulo: "JavaScript Avançado",
  autor: "João Silva",
  paginas: 350,
  ano: 2023,
  disponivel: true,
};

// Regras para nomes de propriedades:
const exemplo = {
  nome: "válido", // ✅ camelCase (recomendado)
  nome_completo: "válido", // ✅ snake_case
  "nome-completo": "válido", // ✅ com aspas (hífen)
  2024: "válido", // ✅ número como string

  // nome-invalido: "erro"     // ❌ hífen sem aspas
  // 2024: "erro"              // ❌ começa com número
};
```

---

## Parte 2: Acessando Propriedades

### 2.1: Notação de Ponto (.)

Forma mais comum e legível para acessar propriedades.

```javascript
const pessoa = {
  nome: "Carlos",
  idade: 30,
  profissao: "Professor",
  cidade: "Rio de Janeiro",
};

// Acessar propriedades
console.log(pessoa.nome); // "Carlos"
console.log(pessoa.idade); // 30
console.log(pessoa.profissao); // "Professor"

// Usar em expressões
const saudacao = "Olá, meu nome é " + pessoa.nome;
console.log(saudacao); // "Olá, meu nome é Carlos"

const idadeEmMeses = pessoa.idade * 12;
console.log(idadeEmMeses); // 360

// Usar em condicionais
if (pessoa.idade >= 18) {
  console.log(pessoa.nome + " é maior de idade");
}
```

### 2.2: Notação de Colchetes []

Útil quando o nome da propriedade é dinâmico ou contém caracteres especiais.

```javascript
const carro = {
  marca: "Ford",
  modelo: "Mustang",
  ano: 2023,
  "cor-principal": "vermelho", // hífen requer colchetes
};

// Acesso normal
console.log(carro["marca"]); // "Ford"
console.log(carro["modelo"]); // "Mustang"

// Propriedade com hífen (só funciona com colchetes)
console.log(carro["cor-principal"]); // "vermelho"
// console.log(carro.cor-principal);  // ❌ ERRO!

// Acesso dinâmico
const propriedade = "ano";
console.log(carro[propriedade]); // 2023

// Exemplo prático: Acesso dinâmico
const usuario = {
  nome: "Ana",
  email: "ana@email.com",
  telefone: "123456789",
};

const campoDesejado = "email"; // Poderia vir de input do usuário
console.log(usuario[campoDesejado]); // "ana@email.com"
```

### 2.3: Propriedades Inexistentes

```javascript
const produto = {
  nome: "Mouse",
  preco: 50.0,
};

console.log(produto.estoque); // undefined (não existe)

// Verificar se propriedade existe
if (produto.estoque !== undefined) {
  console.log("Estoque:", produto.estoque);
} else {
  console.log("Propriedade estoque não existe");
}

// Método melhor: operador in
if ("estoque" in produto) {
  console.log("Tem estoque");
} else {
  console.log("Não tem estoque");
}

// Método moderno: hasOwnProperty
if (produto.hasOwnProperty("preco")) {
  console.log("Produto tem preço definido");
}
```

---

## Parte 3: Modificando Objetos

### 3.1: Alterando Propriedades

```javascript
const pessoa = {
  nome: "Pedro",
  idade: 25,
  cidade: "Brasília",
};

console.log("Antes:", pessoa);

// Modificar propriedades existentes
pessoa.idade = 26;
pessoa.cidade = "São Paulo";

console.log("Depois:", pessoa);
// { nome: "Pedro", idade: 26, cidade: "São Paulo" }

// Exemplo prático: Atualizar perfil
const perfil = {
  usuario: "joao123",
  email: "joao@email.com",
  ativo: true,
};

console.log("Perfil original:", perfil);

// Usuário atualiza email
perfil.email = "joao.novo@email.com";
perfil.ativo = false;

console.log("Perfil atualizado:", perfil);
```

### 3.2: Adicionando Propriedades

```javascript
const livro = {
  titulo: "1984",
  autor: "George Orwell",
};

console.log("Inicial:", livro);

// Adicionar novas propriedades
livro.ano = 1949;
livro.paginas = 328;
livro.disponivel = true;

console.log("Com novas propriedades:", livro);

// Adicionar dinamicamente
const novaProp = "editora";
livro[novaProp] = "Companhia das Letras";

console.log("Final:", livro);
```

### 3.3: Removendo Propriedades

```javascript
const usuario = {
  nome: "Maria",
  email: "maria@email.com",
  senha: "123456", // Não deveria estar aqui!
  telefone: "999999999",
};

console.log("Antes:", usuario);

// Remover propriedade
delete usuario.senha;

console.log("Depois:", usuario);
// { nome: "Maria", email: "maria@email.com", telefone: "999999999" }

// Verificar se foi removida
console.log("senha" in usuario); // false
```

### 3.4: Objetos com const

```javascript
// const impede REATRIBUIÇÃO, mas NÃO impede MODIFICAÇÃO
const carro = {
  marca: "Toyota",
  modelo: "Corolla",
};

// ✅ PODE modificar propriedades
carro.ano = 2023;
carro.cor = "prata";
console.log(carro); // Funciona!

// ❌ NÃO PODE reatribuir o objeto
// carro = { marca: "Honda" };  // ERRO!

// Para objeto realmente imutável, use Object.freeze()
const produtoFixo = Object.freeze({
  nome: "Produto",
  preco: 100,
});

produtoFixo.preco = 200; // Não funciona em modo strict
console.log(produtoFixo.preco); // 100 (não mudou)
```

---

## Parte 4: Métodos de Objetos

### 4.1: O que são Métodos?

**Métodos** são funções que pertencem a um objeto, representando ações ou comportamentos.

```javascript
const pessoa = {
  nome: "Ana",
  idade: 28,

  // Método 1: Função tradicional
  apresentar: function () {
    console.log("Olá, meu nome é " + this.nome);
  },

  // Método 2: Sintaxe curta (ES6) - RECOMENDADO
  saudar() {
    console.log("Oi! Eu tenho " + this.idade + " anos");
  },
};

// Chamar métodos
pessoa.apresentar(); // "Olá, meu nome é Ana"
pessoa.saudar(); // "Oi! Eu tenho 28 anos"
```

### 4.2: A Palavra-chave `this`

`this` se refere ao **próprio objeto** dentro de seus métodos.

```javascript
const conta = {
  titular: "João",
  saldo: 1000.0,

  consultar() {
    console.log("Titular:", this.titular);
    console.log("Saldo: R$", this.saldo.toFixed(2));
  },

  depositar(valor) {
    this.saldo += valor;
    console.log(`Depósito de R$ ${valor.toFixed(2)} realizado`);
    console.log("Novo saldo: R$", this.saldo.toFixed(2));
  },

  sacar(valor) {
    if (valor > this.saldo) {
      console.log("Saldo insuficiente!");
      return false;
    }

    this.saldo -= valor;
    console.log(`Saque de R$ ${valor.toFixed(2)} realizado`);
    console.log("Novo saldo: R$", this.saldo.toFixed(2));
    return true;
  },
};

// Usar métodos
conta.consultar();
conta.depositar(500);
conta.sacar(200);
conta.consultar();
```

### 4.3: Métodos com Parâmetros

```javascript
const calculadora = {
  // Propriedade
  historico: [],

  // Métodos
  somar(a, b) {
    const resultado = a + b;
    this.historico.push(`${a} + ${b} = ${resultado}`);
    return resultado;
  },

  subtrair(a, b) {
    const resultado = a - b;
    this.historico.push(`${a} - ${b} = ${resultado}`);
    return resultado;
  },

  multiplicar(a, b) {
    const resultado = a * b;
    this.historico.push(`${a} × ${b} = ${resultado}`);
    return resultado;
  },

  dividir(a, b) {
    if (b === 0) {
      console.log("Erro: Divisão por zero!");
      return null;
    }
    const resultado = a / b;
    this.historico.push(`${a} ÷ ${b} = ${resultado}`);
    return resultado;
  },

  mostrarHistorico() {
    console.log("\n=== HISTÓRICO DE CÁLCULOS ===");
    for (let i = 0; i < this.historico.length; i++) {
      console.log(`${i + 1}. ${this.historico[i]}`);
    }
  },

  limparHistorico() {
    this.historico = [];
    console.log("Histórico limpo!");
  },
};

// Usar calculadora
console.log(calculadora.somar(10, 5)); // 15
console.log(calculadora.multiplicar(4, 3)); // 12
console.log(calculadora.dividir(20, 4)); // 5
calculadora.mostrarHistorico();
```

### 4.4: Exemplos Práticos Completos

```javascript
// Exemplo 1: Objeto Produto
const produto = {
  id: 1,
  nome: "Notebook",
  preco: 2500.0,
  estoque: 10,

  vender(quantidade) {
    if (quantidade > this.estoque) {
      console.log(`Estoque insuficiente! Disponível: ${this.estoque}`);
      return false;
    }

    this.estoque -= quantidade;
    const total = this.preco * quantidade;

    console.log(`Venda realizada: ${quantidade}x ${this.nome}`);
    console.log(`Valor total: R$ ${total.toFixed(2)}`);
    console.log(`Estoque restante: ${this.estoque}`);

    return true;
  },

  repor(quantidade) {
    this.estoque += quantidade;
    console.log(`${quantidade} unidades repostas`);
    console.log(`Estoque atual: ${this.estoque}`);
  },

  aplicarDesconto(porcentagem) {
    const desconto = this.preco * (porcentagem / 100);
    this.preco -= desconto;

    console.log(`Desconto de ${porcentagem}% aplicado`);
    console.log(`Novo preço: R$ ${this.preco.toFixed(2)}`);
  },

  exibirInfo() {
    console.log("\n=== INFORMAÇÕES DO PRODUTO ===");
    console.log("Nome:", this.nome);
    console.log("Preço: R$", this.preco.toFixed(2));
    console.log("Estoque:", this.estoque, "unidades");
  },
};

// Testar produto
produto.exibirInfo();
produto.vender(3);
produto.repor(5);
produto.aplicarDesconto(10);
produto.exibirInfo();

// Exemplo 2: Objeto Aluno
const aluno = {
  nome: "Carlos Silva",
  matricula: "2024001",
  notas: [],

  adicionarNota(nota) {
    if (nota < 0 || nota > 10) {
      console.log("Nota inválida! Deve estar entre 0 e 10");
      return;
    }

    this.notas.push(nota);
    console.log(`Nota ${nota} adicionada`);
  },

  calcularMedia() {
    if (this.notas.length === 0) {
      return 0;
    }

    let soma = 0;
    for (let i = 0; i < this.notas.length; i++) {
      soma += this.notas[i];
    }

    return soma / this.notas.length;
  },

  situacao() {
    const media = this.calcularMedia();

    console.log("\n=== BOLETIM ===");
    console.log("Aluno:", this.nome);
    console.log("Matrícula:", this.matricula);
    console.log("Notas:", this.notas.join(", "));
    console.log("Média:", media.toFixed(2));

    if (media >= 7) {
      console.log("Situação: APROVADO ✓");
    } else if (media >= 5) {
      console.log("Situação: RECUPERAÇÃO");
    } else {
      console.log("Situação: REPROVADO ✗");
    }
  },
};

// Testar aluno
aluno.adicionarNota(7.5);
aluno.adicionarNota(8.0);
aluno.adicionarNota(6.5);
aluno.adicionarNota(9.0);
aluno.situacao();
```

---

## Parte 5: Objetos Aninhados

### 5.1: Objetos dentro de Objetos

```javascript
const pessoa = {
  nome: "João Silva",
  idade: 30,

  // Objeto aninhado
  endereco: {
    rua: "Av. Principal",
    numero: 123,
    bairro: "Centro",
    cidade: "São Paulo",
    estado: "SP",
    cep: "01000-000",
  },

  // Outro objeto aninhado
  contato: {
    email: "joao@email.com",
    telefone: "(11) 98765-4321",
    linkedin: "linkedin.com/in/joaosilva",
  },
};

// Acessar propriedades aninhadas
console.log(pessoa.nome); // "João Silva"
console.log(pessoa.endereco.cidade); // "São Paulo"
console.log(pessoa.contato.email); // "joao@email.com"

// Modificar propriedades aninhadas
pessoa.endereco.numero = 456;
pessoa.contato.telefone = "(11) 99999-8888";

// Exibir endereço completo
console.log("\nEndereço completo:");
console.log(pessoa.endereco.rua + ", " + pessoa.endereco.numero);
console.log(pessoa.endereco.bairro + " - " + pessoa.endereco.cidade);
console.log("CEP: " + pessoa.endereco.cep);
```

### 5.2: Arrays dentro de Objetos

```javascript
const empresa = {
  nome: "Tech Solutions",
  fundacao: 2020,

  // Array de strings
  funcionarios: ["Ana", "Bruno", "Carlos", "Diana"],

  // Array de objetos
  departamentos: [
    { nome: "TI", funcionarios: 15 },
    { nome: "RH", funcionarios: 5 },
    { nome: "Vendas", funcionarios: 20 },
  ],

  // Método que usa arrays
  totalFuncionarios() {
    let total = 0;
    for (let i = 0; i < this.departamentos.length; i++) {
      total += this.departamentos[i].funcionarios;
    }
    return total;
  },

  listarDepartamentos() {
    console.log("\n=== DEPARTAMENTOS ===");
    for (let i = 0; i < this.departamentos.length; i++) {
      const dept = this.departamentos[i];
      console.log(`${dept.nome}: ${dept.funcionarios} funcionários`);
    }
    console.log(`\nTotal: ${this.totalFuncionarios()} funcionários`);
  },
};

// Usar empresa
console.log("Empresa:", empresa.nome);
console.log("Fundada em:", empresa.fundacao);
console.log("Funcionários:", empresa.funcionarios.join(", "));
empresa.listarDepartamentos();
```

### 5.3: Estruturas Complexas

```javascript
const escola = {
  nome: "Colégio Exemplo",
  endereco: "Rua da Escola, 100",

  turmas: [
    {
      serie: "9º Ano A",
      sala: 201,
      alunos: [
        { nome: "Ana", notas: [8.0, 7.5, 9.0] },
        { nome: "Bruno", notas: [7.0, 8.0, 7.5] },
        { nome: "Carlos", notas: [9.0, 9.5, 8.5] },
      ],
    },
    {
      serie: "9º Ano B",
      sala: 202,
      alunos: [
        { nome: "Diana", notas: [7.5, 8.0, 8.5] },
        { nome: "Eduardo", notas: [6.0, 7.0, 6.5] },
      ],
    },
  ],

  relatorioCompleto() {
    console.log("========================================");
    console.log(`   RELATÓRIO - ${this.nome}`);
    console.log("========================================\n");

    for (let i = 0; i < this.turmas.length; i++) {
      const turma = this.turmas[i];

      console.log(`--- ${turma.serie} (Sala ${turma.sala}) ---\n`);

      for (let j = 0; j < turma.alunos.length; j++) {
        const aluno = turma.alunos[j];

        // Calcular média
        let soma = 0;
        for (let k = 0; k < aluno.notas.length; k++) {
          soma += aluno.notas[k];
        }
        const media = soma / aluno.notas.length;

        // Exibir
        console.log(`${aluno.nome}:`);
        console.log(`  Notas: ${aluno.notas.join(", ")}`);
        console.log(`  Média: ${media.toFixed(2)}`);
        console.log(`  Situação: ${media >= 7 ? "Aprovado" : "Reprovado"}\n`);
      }
    }
  },
};

// Gerar relatório
escola.relatorioCompleto();
```

---

## Parte 6: Arrays de Objetos

### 6.1: Criando Arrays de Objetos

```javascript
// Array de objetos - estrutura muito comum!
const produtos = [
  {
    id: 1,
    nome: "Notebook",
    preco: 2500.0,
    estoque: 10,
  },
  {
    id: 2,
    nome: "Mouse",
    preco: 50.0,
    estoque: 50,
  },
  {
    id: 3,
    nome: "Teclado",
    preco: 150.0,
    estoque: 30,
  },
];

// Acessar elementos
console.log(produtos[0].nome); // "Notebook"
console.log(produtos[1].preco); // 50.00
console.log(produtos[2].estoque); // 30
```

### 6.2: Iterando sobre Arrays de Objetos

```javascript
const alunos = [
  { nome: "Ana", nota: 8.5 },
  { nome: "Bruno", nota: 7.0 },
  { nome: "Carlos", nota: 9.0 },
  { nome: "Diana", nota: 6.5 },
];

// Exemplo 1: Listar todos
console.log("=== LISTA DE ALUNOS ===\n");

for (let i = 0; i < alunos.length; i++) {
  console.log(`${i + 1}. ${alunos[i].nome} - Nota: ${alunos[i].nota}`);
}

// Exemplo 2: Calcular média geral
let somaNotas = 0;

for (let i = 0; i < alunos.length; i++) {
  somaNotas += alunos[i].nota;
}

const mediaGeral = somaNotas / alunos.length;
console.log(`\nMédia geral da turma: ${mediaGeral.toFixed(2)}`);

// Exemplo 3: Filtrar aprovados (nota >= 7)
console.log("\n=== ALUNOS APROVADOS ===\n");

for (let i = 0; i < alunos.length; i++) {
  if (alunos[i].nota >= 7) {
    console.log(`✓ ${alunos[i].nome}`);
  }
}

// Exemplo 4: Encontrar maior nota
let maiorNota = alunos[0];

for (let i = 1; i < alunos.length; i++) {
  if (alunos[i].nota > maiorNota.nota) {
    maiorNota = alunos[i];
  }
}

console.log(`\nMelhor aluno: ${maiorNota.nome} (${maiorNota.nota})`);
```

### 6.3: Manipulando Arrays de Objetos

```javascript
const carrinho = [
  { produto: "Notebook", preco: 2500, quantidade: 1 },
  { produto: "Mouse", preco: 50, quantidade: 2 },
  { produto: "Teclado", preco: 150, quantidade: 1 },
];

// Adicionar novo produto
carrinho.push({
  produto: "Monitor",
  preco: 800,
  quantidade: 1,
});

// Calcular total do carrinho
let total = 0;

for (let i = 0; i < carrinho.length; i++) {
  const item = carrinho[i];
  const subtotal = item.preco * item.quantidade;
  total += subtotal;

  console.log(
    `${item.produto}: ${item.quantidade}x R$ ${item.preco.toFixed(
      2
    )} = R$ ${subtotal.toFixed(2)}`
  );
}

console.log(`\nTOTAL: R$ ${total.toFixed(2)}`);

// Atualizar quantidade de um produto
for (let i = 0; i < carrinho.length; i++) {
  if (carrinho[i].produto === "Mouse") {
    carrinho[i].quantidade = 3;
    console.log("\nQuantidade de Mouse atualizada!");
  }
}

// Remover produto
for (let i = 0; i < carrinho.length; i++) {
  if (carrinho[i].produto === "Teclado") {
    carrinho.splice(i, 1);
    console.log("Teclado removido do carrinho!");
    break;
  }
}
```

### 6.4: Busca em Arrays de Objetos

```javascript
const usuarios = [
  { id: 1, nome: "João", email: "joao@email.com", ativo: true },
  { id: 2, nome: "Maria", email: "maria@email.com", ativo: true },
  { id: 3, nome: "Pedro", email: "pedro@email.com", ativo: false },
  { id: 4, nome: "Ana", email: "ana@email.com", ativo: true },
];

// Buscar por ID
function buscarPorId(id) {
  for (let i = 0; i < usuarios.length; i++) {
    if (usuarios[i].id === id) {
      return usuarios[i];
    }
  }
  return null; // Não encontrado
}

const usuario = buscarPorId(2);
if (usuario) {
  console.log("Usuário encontrado:", usuario.nome);
} else {
  console.log("Usuário não encontrado");
}

// Buscar por email
function buscarPorEmail(email) {
  for (let i = 0; i < usuarios.length; i++) {
    if (usuarios[i].email === email) {
      return usuarios[i];
    }
  }
  return null;
}

// Listar apenas usuários ativos
console.log("\n=== USUÁRIOS ATIVOS ===");

for (let i = 0; i < usuarios.length; i++) {
  if (usuarios[i].ativo) {
    console.log(`- ${usuarios[i].nome} (${usuarios[i].email})`);
  }
}
```

---

## 🎓 Parte 7: Exercícios Práticos

### Exercício 1: Criar e Acessar Objeto ⭐

**Objetivo:** Praticar criação e acesso básico.

**Tarefa:**

```javascript
// 1. Crie um objeto "carro" com propriedades:
//    - marca
//    - modelo
//    - ano
//    - cor
// 2. Exiba cada propriedade
// 3. Modifique a cor do carro
// 4. Adicione propriedade "km" (quilometragem)
// 5. Exiba o objeto completo
```

---

### Exercício 2: Objeto com Método ⭐

**Objetivo:** Criar métodos simples.

**Tarefa:**

```javascript
// Crie um objeto "retangulo" com:
// - Propriedades: largura e altura
// - Método calcularArea() que retorna largura * altura
// - Método calcularPerimetro() que retorna 2 * (largura + altura)
//
// Teste os métodos
```

---

### Exercício 3: Objeto Conta Bancária ⭐⭐

**Objetivo:** Criar objeto com múltiplos métodos.

**Tarefa:**

```javascript
// Crie um objeto "contaBancaria" com:
// - Propriedades: titular, saldo
// - Método depositar(valor)
// - Método sacar(valor) - verificar se tem saldo
// - Método consultarSaldo()
//
// Teste todas as operações
```

---

### Exercício 4: Array de Objetos ⭐⭐

**Objetivo:** Trabalhar com lista de objetos.

**Tarefa:**

```javascript
const livros = [
  { titulo: "1984", autor: "George Orwell", paginas: 328 },
  { titulo: "O Senhor dos Anéis", autor: "Tolkien", paginas: 1200 },
  { titulo: "Harry Potter", autor: "J.K. Rowling", paginas: 450 },
];

// 1. Liste todos os livros
// 2. Encontre o livro com mais páginas
// 3. Calcule o total de páginas
// 4. Adicione um novo livro
```

---

### Exercício 5: Busca em Objetos ⭐⭐

**Objetivo:** Procurar informações em objetos.

**Tarefa:**

```javascript
const produtos = [
  { id: 1, nome: "Notebook", preco: 2500 },
  { id: 2, nome: "Mouse", preco: 50 },
  { id: 3, nome: "Teclado", preco: 150 },
];

// 1. Crie função buscarPorId(id) que retorna o produto
// 2. Crie função buscarPorNome(nome) que retorna o produto
// 3. Teste as funções
```

---

### Exercício 6: Objeto Aninhado ⭐⭐⭐

**Objetivo:** Trabalhar com objetos complexos.

**Tarefa:**

```javascript
// Crie um objeto "empresa" com:
// - nome
// - funcionarios (array de objetos com nome e salario)
// - Método adicionarFuncionario(nome, salario)
// - Método calcularFolhaPagamento() - soma todos os salários
// - Método funcionarioMaiorSalario() - retorna nome

// Adicione 4 funcionários e teste os métodos
```

---

### Exercício 7: Carrinho de Compras ⭐⭐⭐

**Objetivo:** Sistema completo com objetos.

**Tarefa:**

```javascript
const carrinho = {
  itens: [],

  adicionar(produto, preco, quantidade) {
    // Adiciona item ao array itens
  },

  remover(produto) {
    // Remove item do array
  },

  calcularTotal() {
    // Retorna soma de todos os itens
  },

  listar() {
    // Exibe todos os itens formatados
  },
};

// Teste o carrinho:
// - Adicione 3 produtos
// - Liste os itens
// - Remova 1 produto
// - Mostre o total
```

---

### Exercício 8: Sistema de Notas ⭐⭐⭐

**Objetivo:** Objeto complexo com cálculos.

**Tarefa:**

```javascript
const turma = {
  nome: "Turma A",
  alunos: [],

  adicionarAluno(nome) {
    // Adiciona {nome: nome, notas: []}
  },

  adicionarNota(nomeAluno, nota) {
    // Encontra aluno e adiciona nota
  },

  calcularMediaAluno(nomeAluno) {
    // Retorna média do aluno
  },

  relatorio() {
    // Exibe todos os alunos com suas médias
  },
};

// Adicione 3 alunos
// Adicione 3 notas para cada
// Gere relatório
```

---

### Exercício 9: Cadastro de Produtos ⭐⭐⭐

**Objetivo:** CRUD completo (Create, Read, Update, Delete).

**Tarefa:**

```javascript
const estoque = {
  produtos: [],
  proximoId: 1,

  cadastrar(nome, preco, quantidade) {
    // Cria produto com id auto-incremento
  },

  buscar(id) {
    // Retorna produto ou null
  },

  atualizar(id, novosDados) {
    // Atualiza propriedades do produto
  },

  remover(id) {
    // Remove produto do array
  },

  listar() {
    // Exibe todos os produtos
  },
};

// Teste todas as operações
```

---

### Exercício 10: Agenda de Contatos ⭐⭐⭐

**Objetivo:** Sistema completo com múltiplas funcionalidades.

**Tarefa:**

```javascript
const agenda = {
  contatos: [],

  adicionar(nome, telefone, email) {
    // Valida se contato já existe
    // Adiciona ao array
  },

  buscarPorNome(nome) {
    // Retorna contato(s) que contém o nome
  },

  atualizar(nome, novoTelefone, novoEmail) {
    // Atualiza dados do contato
  },

  remover(nome) {
    // Remove contato
  },

  listarTodos() {
    // Exibe todos ordenados por nome
  },

  total() {
    // Retorna quantidade de contatos
  },
};

// Adicione 5 contatos
// Busque um contato
// Atualize um contato
// Remova um contato
// Liste todos
```

---

## Parte 8: Desafios Avançados (Opcional)

### Desafio 1: Sistema de Biblioteca 🔥🔥🔥

```javascript
const biblioteca = {
  livros: [],
  emprestimos: [],

  cadastrarLivro(titulo, autor, isbn) {
    // Adiciona livro com status "disponivel"
  },

  emprestar(isbn, nomeUsuario) {
    // Verifica disponibilidade
    // Registra empréstimo com data
    // Muda status do livro
  },

  devolver(isbn) {
    // Registra devolução
    // Libera livro
  },

  livrosDisponiveis() {
    // Retorna array de livros disponíveis
  },

  historicoUsuario(nome) {
    // Mostra empréstimos do usuário
  },

  relatorioCompleto() {
    // Estatísticas gerais
  },
};

// Implemente e teste o sistema completo
```

---

### Desafio 2: Jogo de RPG Simplificado 🔥🔥🔥

```javascript
const personagem = {
  nome: "",
  nivel: 1,
  vida: 100,
  mana: 50,
  experiencia: 0,
  inventario: [],

  atacar(inimigo) {
    // Calcula dano baseado no nível
    // Reduz vida do inimigo
    // Ganha experiência
  },

  usarMagia(inimigo) {
    // Verifica se tem mana
    // Causa dano mágico
    // Consome mana
  },

  curar() {
    // Usa mana para recuperar vida
  },

  subirNivel() {
    // Aumenta atributos
  },

  adicionarItem(item) {
    // Adiciona ao inventário
  },

  status() {
    // Exibe todos os atributos
  },
};

const inimigo = {
  nome: "Goblin",
  vida: 50,
  dano: 10,
};

// Crie um combate entre personagem e inimigo
```

---

### Desafio 3: Sistema de Pedidos de Restaurante 🔥🔥🔥

```javascript
const restaurante = {
  menu: [
    { id: 1, nome: "Pizza", preco: 35.0, categoria: "Prato Principal" },
    { id: 2, nome: "Refrigerante", preco: 5.0, categoria: "Bebida" },
    // ... mais itens
  ],

  pedidos: [],
  proximoPedido: 1,

  exibirMenu() {
    // Mostra menu por categoria
  },

  fazerPedido(mesa, itens) {
    // itens = [{id: 1, quantidade: 2}, ...]
    // Cria pedido com número, mesa, itens, total
    // Retorna número do pedido
  },

  calcularConta(numeroPedido) {
    // Calcula total + taxa de serviço (10%)
  },

  fecharConta(numeroPedido) {
    // Exibe conta detalhada
    // Remove pedido
  },

  pedidosAbertos() {
    // Lista pedidos em aberto
  },
};

// Simule 3 pedidos diferentes
// Feche as contas
```

---

## Parte 9: Projeto da Semana

### 🎯 Sistema de Gerenciamento de Alunos

**Objetivo:** Criar um sistema completo de gestão acadêmica.

```javascript
const sistemaAcademico = {
  alunos: [],
  proximaMatricula: 20240001,

  // ===== PARTE 1: CADASTRO =====
  cadastrarAluno(nome, dataNascimento, curso) {
    const aluno = {
      matricula: this.proximaMatricula++,
      nome: nome,
      dataNascimento: dataNascimento,
      curso: curso,
      disciplinas: [],
      ativo: true,
    };

    this.alunos.push(aluno);
    console.log(`✓ Aluno ${nome} cadastrado com matrícula ${aluno.matricula}`);
    return aluno.matricula;
  },

  // ===== PARTE 2: BUSCA =====
  buscarPorMatricula(matricula) {
    for (let i = 0; i < this.alunos.length; i++) {
      if (this.alunos[i].matricula === matricula) {
        return this.alunos[i];
      }
    }
    return null;
  },

  buscarPorNome(nome) {
    const resultado = [];
    const nomeBusca = nome.toLowerCase();

    for (let i = 0; i < this.alunos.length; i++) {
      const nomeAluno = this.alunos[i].nome.toLowerCase();
      if (nomeAluno.includes(nomeBusca)) {
        resultado.push(this.alunos[i]);
      }
    }

    return resultado;
  },

  // ===== PARTE 3: DISCIPLINAS =====
  matricularDisciplina(matricula, nomeDisciplina) {
    const aluno = this.buscarPorMatricula(matricula);

    if (!aluno) {
      console.log("Aluno não encontrado!");
      return false;
    }

    // Verificar se já está matriculado
    for (let i = 0; i < aluno.disciplinas.length; i++) {
      if (aluno.disciplinas[i].nome === nomeDisciplina) {
        console.log("Aluno já matriculado nesta disciplina!");
        return false;
      }
    }

    aluno.disciplinas.push({
      nome: nomeDisciplina,
      notas: [],
      faltas: 0,
    });

    console.log(`✓ ${aluno.nome} matriculado em ${nomeDisciplina}`);
    return true;
  },

  // ===== PARTE 4: NOTAS =====
  lancarNota(matricula, nomeDisciplina, nota) {
    const aluno = this.buscarPorMatricula(matricula);

    if (!aluno) {
      console.log("Aluno não encontrado!");
      return;
    }

    // Validar nota
    if (nota < 0 || nota > 10) {
      console.log("Nota inválida! Deve estar entre 0 e 10");
      return;
    }

    // Encontrar disciplina
    for (let i = 0; i < aluno.disciplinas.length; i++) {
      if (aluno.disciplinas[i].nome === nomeDisciplina) {
        aluno.disciplinas[i].notas.push(nota);
        console.log(
          `✓ Nota ${nota} lançada para ${aluno.nome} em ${nomeDisciplina}`
        );
        return;
      }
    }

    console.log("Disciplina não encontrada!");
  },

  calcularMedia(matricula, nomeDisciplina) {
    const aluno = this.buscarPorMatricula(matricula);

    if (!aluno) return null;

    for (let i = 0; i < aluno.disciplinas.length; i++) {
      if (aluno.disciplinas[i].nome === nomeDisciplina) {
        const notas = aluno.disciplinas[i].notas;

        if (notas.length === 0) return 0;

        let soma = 0;
        for (let j = 0; j < notas.length; j++) {
          soma += notas[j];
        }

        return soma / notas.length;
      }
    }

    return null;
  },

  // ===== PARTE 5: FALTAS =====
  registrarFalta(matricula, nomeDisciplina) {
    const aluno = this.buscarPorMatricula(matricula);

    if (!aluno) {
      console.log("Aluno não encontrado!");
      return;
    }

    for (let i = 0; i < aluno.disciplinas.length; i++) {
      if (aluno.disciplinas[i].nome === nomeDisciplina) {
        aluno.disciplinas[i].faltas++;
        console.log(`Falta registrada. Total: ${aluno.disciplinas[i].faltas}`);
        return;
      }
    }

    console.log("Disciplina não encontrada!");
  },

  // ===== PARTE 6: BOLETIM =====
  gerarBoletim(matricula) {
    const aluno = this.buscarPorMatricula(matricula);

    if (!aluno) {
      console.log("Aluno não encontrado!");
      return;
    }

    console.log("\n========================================");
    console.log("              BOLETIM ESCOLAR           ");
    console.log("========================================");
    console.log(`Aluno: ${aluno.nome}`);
    console.log(`Matrícula: ${aluno.matricula}`);
    console.log(`Curso: ${aluno.curso}`);
    console.log("========================================\n");

    if (aluno.disciplinas.length === 0) {
      console.log("Nenhuma disciplina matriculada.\n");
      return;
    }

    for (let i = 0; i < aluno.disciplinas.length; i++) {
      const disc = aluno.disciplinas[i];
      const media = this.calcularMedia(matricula, disc.nome);

      console.log(`DISCIPLINA: ${disc.nome}`);
      console.log(
        `Notas: ${disc.notas.length > 0 ? disc.notas.join(", ") : "Sem notas"}`
      );
      console.log(`Média: ${media ? media.toFixed(2) : "N/A"}`);
      console.log(`Faltas: ${disc.faltas}`);

      if (media !== null) {
        if (media >= 7 && disc.faltas < 18) {
          console.log("Situação: APROVADO ✓");
        } else if (disc.faltas >= 18) {
          console.log("Situação: REPROVADO POR FALTA ✗");
        } else if (media >= 5) {
          console.log("Situação: RECUPERAÇÃO");
        } else {
          console.log("Situação: REPROVADO POR NOTA ✗");
        }
      }

      console.log("----------------------------------------\n");
    }
  },

  // ===== PARTE 7: RELATÓRIOS =====
  listarTodosAlunos() {
    console.log("\n=== LISTA DE ALUNOS ===\n");

    if (this.alunos.length === 0) {
      console.log("Nenhum aluno cadastrado.\n");
      return;
    }

    for (let i = 0; i < this.alunos.length; i++) {
      const aluno = this.alunos[i];
      console.log(`${i + 1}. ${aluno.nome} - Mat: ${aluno.matricula}`);
      console.log(`   Curso: ${aluno.curso}`);
      console.log(`   Disciplinas: ${aluno.disciplinas.length}`);
      console.log("");
    }
  },

  estatisticas() {
    console.log("\n=== ESTATÍSTICAS DO SISTEMA ===\n");
    console.log(`Total de alunos: ${this.alunos.length}`);

    // Contar por curso
    const cursos = {};
    for (let i = 0; i < this.alunos.length; i++) {
      const curso = this.alunos[i].curso;
      cursos[curso] = (cursos[curso] || 0) + 1;
    }

    console.log("\nAlunos por curso:");
    for (let curso in cursos) {
      console.log(`  ${curso}: ${cursos[curso]} alunos`);
    }

    console.log("");
  },
};

// ===== TESTE DO SISTEMA =====

console.log("===== INICIANDO SISTEMA ACADÊMICO =====\n");

// 1. Cadastrar alunos
const mat1 = sistemaAcademico.cadastrarAluno(
  "Ana Silva",
  "15/03/2005",
  "Ciência da Computação"
);
const mat2 = sistemaAcademico.cadastrarAluno(
  "Bruno Costa",
  "22/07/2004",
  "Engenharia"
);
const mat3 = sistemaAcademico.cadastrarAluno(
  "Carlos Souza",
  "10/11/2005",
  "Ciência da Computação"
);

// 2. Matricular em disciplinas
console.log("\n--- Matriculando em disciplinas ---\n");
sistemaAcademico.matricularDisciplina(mat1, "Programação");
sistemaAcademico.matricularDisciplina(mat1, "Banco de Dados");
sistemaAcademico.matricularDisciplina(mat2, "Cálculo I");
sistemaAcademico.matricularDisciplina(mat3, "Programação");

// 3. Lançar notas
console.log("\n--- Lançando notas ---\n");
sistemaAcademico.lancarNota(mat1, "Programação", 8.5);
sistemaAcademico.lancarNota(mat1, "Programação", 9.0);
sistemaAcademico.lancarNota(mat1, "Programação", 7.5);

sistemaAcademico.lancarNota(mat1, "Banco de Dados", 7.0);
sistemaAcademico.lancarNota(mat1, "Banco de Dados", 8.0);

sistemaAcademico.lancarNota(mat3, "Programação", 9.5);
sistemaAcademico.lancarNota(mat3, "Programação", 10.0);

// 4. Registrar faltas
console.log("\n--- Registrando faltas ---\n");
sistemaAcademico.registrarFalta(mat1, "Programação");
sistemaAcademico.registrarFalta(mat1, "Programação");
sistemaAcademico.registrarFalta(mat1, "Banco de Dados");

// 5. Gerar boletins
sistemaAcademico.gerarBoletim(mat1);
sistemaAcademico.gerarBoletim(mat3);

// 6. Relatórios gerais
sistemaAcademico.listarTodosAlunos();
sistemaAcademico.estatisticas();

// 7. Buscar alunos
console.log("=== BUSCA DE ALUNOS ===\n");
const resultado = sistemaAcademico.buscarPorNome("Silva");
console.log(`Encontrados ${resultado.length} aluno(s) com "Silva":`);
for (let i = 0; i < resultado.length; i++) {
  console.log(`- ${resultado[i].nome}`);
}
```

**Critérios de avaliação:**

- [ ] Cadastra alunos corretamente
- [ ] Matricula em disciplinas
- [ ] Lança notas com validação
- [ ] Registra faltas
- [ ] Calcula médias corretamente
- [ ] Gera boletim completo
- [ ] Busca alunos por matrícula e nome
- [ ] Lista todos os alunos
- [ ] Gera estatísticas
- [ ] Valida dados de entrada
- [ ] Usa objetos e arrays corretamente
- [ ] Código organizado e comentado

**Desafios extras:**

- Adicione método para trancar disciplina
- Implemente histórico de notas alteradas
- Crie ranking de melhores alunos
- Adicione data de matrícula e cálculo de idade
- Implemente transferência de curso

---

## Parte 10: Checklist de Aprendizado

Ao final da Semana 6, você deve ser capaz de:

- [ ] Criar objetos com notação literal
- [ ] Acessar propriedades (ponto e colchetes)
- [ ] Modificar e adicionar propriedades
- [ ] Remover propriedades com delete
- [ ] Criar métodos de objetos
- [ ] Usar this dentro de métodos
- [ ] Trabalhar com objetos aninhados
- [ ] Criar e manipular arrays de objetos
- [ ] Iterar sobre arrays de objetos
- [ ] Buscar e filtrar objetos
- [ ] Criar estruturas complexas
- [ ] Combinar objetos com loops
- [ ] Resolver problemas com objetos
- [ ] Modelar entidades do mundo real

---

## Parte 11: Troubleshooting

### Problema 1: this undefined

```javascript
const pessoa = {
  nome: "João",
  apresentar: function () {
    console.log(this.nome); // ✅ Funciona
  },
};

// ❌ PROBLEMA com arrow function
const pessoa2 = {
  nome: "Maria",
  apresentar: () => {
    console.log(this.nome); // undefined!
  },
};

// ✅ SOLUÇÃO: Use function normal em métodos
```

### Problema 2: Modificar objeto const

```javascript
const obj = { valor: 10 };

// ✅ PODE modificar propriedades
obj.valor = 20; // Funciona

// ❌ NÃO PODE reatribuir
obj = { valor: 30 }; // ERRO!
```

### Problema 3: Copiar objeto (referência)

```javascript
const original = { nome: "João" };
const copia = original; // ❌ Não é cópia!

copia.nome = "Maria";
console.log(original.nome); // "Maria" - modificou o original!

// ✅ SOLUÇÃO: Copiar propriedades
const copiaReal = { ...original }; // Spread operator
// ou
const copiaReal2 = Object.assign({}, original);
```

### Problema 4: Acessar propriedade inexistente

```javascript
const obj = { nome: "João" };

console.log(obj.idade); // undefined (não dá erro)

// ✅ Verificar antes
if (obj.idade !== undefined) {
  console.log(obj.idade);
} else {
  console.log("Propriedade não existe");
}
```

---

## Parte 12: Boas Práticas

### ✅ FAÇA:

1. **Use const para objetos**

```javascript
const usuario = { nome: "João" }; // ✅
```

2. **Nomes de propriedades em camelCase**

```javascript
const pessoa = {
  nomeCompleto: "João", // ✅
  dataDeNascimento: "01/01/2000",
};
```

3. **Métodos com função normal (não arrow)**

```javascript
const obj = {
  metodo() {
    // ✅ Sintaxe curta
    return this.propriedade;
  },
};
```

4. **Valide dados em métodos**

```javascript
depositar(valor) {
    if (valor <= 0) {
        console.log("Valor inválido!");
        return false;
    }
    // código...
}
```

### ❌ EVITE:

1. **Objetos muito grandes em uma linha**

```javascript
// ❌ Difícil de ler
const obj = { prop1: "a", prop2: "b", prop3: "c", prop4: "d" };

// ✅ Melhor
const obj = {
  prop1: "a",
  prop2: "b",
  prop3: "c",
  prop4: "d",
};
```

2. **Arrow functions em métodos**

```javascript
// ❌
const obj = {
  metodo: () => this.prop, // this não funciona!
};
```

3. **Muitos níveis de aninhamento**

```javascript
// ❌ Muito aninhado
obj.nivel1.nivel2.nivel3.nivel4.prop;
```

---

## Recursos Adicionais

### Documentação:

- **MDN - Objetos**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Working_with_Objects
- **JavaScript.info - Objetos**: https://javascript.info/object

### Ferramentas:

- **JSON Formatter**: jsonformatter.org
- **Object Explorer**: objectexplorer.netlify.app

---

## Preparação para Semana 7

Na próxima semana você aprenderá:

- ✨ Funções avançadas
- ✨ Arrow functions
- ✨ Callbacks
- ✨ Escopo e closures

**Pré-requisito:** Domine objetos e métodos!

---

**Professor:** Marcelo Damasceno de Melo

**Curso:** Introdução ao JavaScript

**Semana:** 6 de 8

**Próxima aula:** Funções Avançadas

---

**Bons estudos! 🚀**
