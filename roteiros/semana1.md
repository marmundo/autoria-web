# Roteiro de Estudos: Introdução ao JavaScript - Semana 1

## Objetivo da Semana

Compreender os fundamentos básicos do JavaScript, aprender a declarar variáveis corretamente e dominar os tipos de dados primitivos da linguagem, preparando a base para conceitos mais avançados.

---

## ⚠️ AVISO IMPORTANTE SOBRE AMBIENTE DE DESENVOLVIMENTO

**ATENÇÃO:** Para seguir este roteiro você precisará:

- **Navegador moderno** (Chrome, Firefox, Edge ou Safari atualizado)
- **Editor de código** (VS Code recomendado - gratuito)
- **Acesso ao Console do navegador** (F12 ou Ctrl+Shift+J)

**Para este roteiro:**

- Todos os exercícios podem ser feitos diretamente no console do navegador
- Recomenda-se criar arquivos HTML simples para prática
- Não é necessário instalar Node.js nesta primeira semana

---

## Parte 1: O que é JavaScript?

### Passo 1.1: História e Contexto

JavaScript é uma linguagem de programação criada em 1995 por Brendan Eich para adicionar interatividade às páginas web. Hoje é uma das linguagens mais populares do mundo.

**Características principais:**

- Linguagem **interpretada** (não precisa compilar)
- **Multiplataforma** (roda no navegador e servidor)
- **Dinamicamente tipada** (não precisa declarar tipos)
- **Case-sensitive** (diferencia maiúsculas de minúsculas)

### Passo 1.2: JavaScript vs Java vs ECMAScript

**Diferenças importantes:**

| Aspecto | JavaScript | Java |
|---------|-----------|------|
| Tipo | Interpretada | Compilada |
| Tipagem | Dinâmica | Estática |
| Uso principal | Web (front-end/back-end) | Aplicações empresariais |

**ECMAScript (ES):** É a especificação/padrão que JavaScript segue. Versões: ES5, ES6 (ES2015), ES2020, etc.

### Passo 1.3: Onde JavaScript é executado?

1. **Navegador (Front-end)**
   - Chrome (V8 engine)
   - Firefox (SpiderMonkey)
   - Safari (JavaScriptCore)

2. **Servidor (Back-end)**
   - Node.js
   - Deno

---

## Parte 2: Configurando o Ambiente

### Opção 1: Console do Navegador (RECOMENDADO para iniciantes)

**Google Chrome:**

1. Abra o Chrome
2. Pressione `F12` ou `Ctrl + Shift + J` (Windows/Linux)
3. Pressione `Cmd + Option + J` (Mac)
4. Selecione a aba "Console"

**Teste seu primeiro código:**

```javascript
console.log("Olá, JavaScript!");
```

### Opção 2: Arquivo HTML + JavaScript (MELHOR PRÁTICA)

**Passo 1: Criar estrutura de pastas**

```
meu-projeto-js/
├── index.html
└── script.js
```

**Passo 2: Criar arquivo HTML**

**Arquivo: `index.html`**

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Primeiro JavaScript</title>
</head>
<body>
    <h1>Estudando JavaScript - Semana 1</h1>
    <p>Abra o Console (F12) para ver os resultados!</p>
    
    <!-- JavaScript externo (RECOMENDADO) -->
    <script src="script.js"></script>
</body>
</html>
```

**Passo 3: Criar arquivo JavaScript**

**Arquivo: `script.js`**

```javascript
// Meu primeiro programa em JavaScript
console.log("JavaScript carregado com sucesso!");
console.log("Bem-vindo ao curso!");
```

**Passo 4: Abrir no navegador**

1. Clique duas vezes no `index.html`
2. Abra o Console (F12)
3. Veja suas mensagens aparecerem

### Opção 3: JavaScript Inline (NÃO recomendado para projetos)

```html
<!DOCTYPE html>
<html>
<body>
    <h1>Teste Rápido</h1>
    
    <script>
        console.log("JavaScript inline");
    </script>
</body>
</html>
```

---

## Parte 3: Primeiro Programa - Console.log()

### 3.1: O que é console.log()?

É o comando usado para **imprimir/exibir** informações no console do navegador. Essencial para debugar e testar código.

**Sintaxe básica:**

```javascript
console.log("mensagem aqui");
```

### 3.2: Exemplos Práticos

```javascript
// Texto simples
console.log("Olá, Mundo!");

// Múltiplas mensagens
console.log("Nome:", "João");
console.log("Idade:", 25);

// Expressões matemáticas
console.log(10 + 5);  // 15
console.log(20 - 8);  // 12

// Múltiplos valores separados por vírgula
console.log("Resultado:", 10 + 5, "pontos");
```

### 3.3: Outros métodos do Console

```javascript
console.warn("Isto é um aviso!");     // Amarelo
console.error("Isto é um erro!");     // Vermelho
console.info("Informação importante"); // Azul
console.table([1, 2, 3]);             // Formato tabela
```

---

## Parte 4: Variáveis - Armazenando Dados

### 4.1: O que são Variáveis?

Variáveis são **containers** (caixas) que armazenam dados na memória do computador. Cada variável tem um **nome** e um **valor**.

**Analogia:** Pense em uma variável como uma caixa etiquetada onde você guarda algo.

### 4.2: Três formas de declarar variáveis

#### A) `var` - A forma antiga (evite usar)

```javascript
var nome = "Maria";
var idade = 30;

// Problemas do var:
var x = 10;
var x = 20;  // Pode redeclarar (ruim!)
console.log(x);  // 20
```

**Por que evitar `var`?**
- Pode ser redeclarado acidentalmente
- Escopo confuso (veremos mais tarde)
- ES6 trouxe alternativas melhores

#### B) `let` - Para valores que PODEM mudar

```javascript
let nome = "João";
console.log(nome);  // "João"

// Posso REATRIBUIR
nome = "Pedro";
console.log(nome);  // "Pedro"

// NÃO posso REDECLARAR
// let nome = "Carlos";  // ❌ ERRO!
```

**Quando usar `let`?**
- Contadores
- Valores que serão atualizados
- Variáveis de loop

#### C) `const` - Para valores CONSTANTES

```javascript
const PI = 3.14159;
console.log(PI);  // 3.14159

// NÃO posso reatribuir
// PI = 3.14;  // ❌ ERRO!

// NÃO posso redeclarar
// const PI = 3.15;  // ❌ ERRO!
```

**Quando usar `const`?**
- Valores fixos
- Configurações
- Referências que não mudam
- **USE `const` POR PADRÃO**

### 4.3: Regras de Nomenclatura

**✅ PERMITIDO:**

```javascript
let nome;           // minúsculas
let nomeCompleto;   // camelCase (RECOMENDADO)
let nome_completo;  // snake_case
let idade2;         // números (não no início)
let $valor;         // cifrão
let _privado;       // underscore
```

**❌ NÃO PERMITIDO:**

```javascript
let 2nome;          // começa com número
let nome-completo;  // hífen
let nome completo;  // espaço
let class;          // palavra reservada
```

**📋 Convenções (boas práticas):**

```javascript
// camelCase para variáveis e funções
let nomeDoUsuario = "Ana";
let calcularTotal = function() {};

// PascalCase para classes
class UsuarioAdmin {}

// UPPER_CASE para constantes globais
const API_URL = "https://api.exemplo.com";
const MAX_TENTATIVAS = 3;
```

### 4.4: Exemplos Práticos Completos

```javascript
// Dados de um usuário
const nomeUsuario = "Carlos Silva";
let idadeUsuario = 28;
let emailUsuario = "carlos@email.com";

console.log("Nome:", nomeUsuario);
console.log("Idade:", idadeUsuario);
console.log("Email:", emailUsuario);

// Atualizando dados
idadeUsuario = 29;  // ✅ Funciona (let)
// nomeUsuario = "Carlos Santos";  // ❌ Erro (const)

// Calculando ano de nascimento
const anoAtual = 2025;
let anoNascimento = anoAtual - idadeUsuario;
console.log("Ano de nascimento:", anoNascimento);
```

---

## Parte 5: Tipos de Dados Primitivos

### 5.1: O que são Tipos de Dados?

JavaScript tem **7 tipos primitivos**. Nesta semana veremos os 5 principais.

### 5.2: String (Texto)

Sequência de caracteres entre aspas.

```javascript
// Três formas de declarar strings
let nome1 = "João";      // aspas duplas
let nome2 = 'Maria';     // aspas simples
let nome3 = `Pedro`;     // template literals (ES6)

// Concatenação (juntar textos)
let primeiroNome = "Ana";
let sobrenome = "Silva";
let nomeCompleto = primeiroNome + " " + sobrenome;
console.log(nomeCompleto);  // "Ana Silva"

// Template literals (MODERNO)
let idade = 25;
let mensagem = `Olá, meu nome é ${primeiroNome} e tenho ${idade} anos`;
console.log(mensagem);

// Propriedades e métodos básicos
let texto = "JavaScript";
console.log(texto.length);        // 10 (tamanho)
console.log(texto.toUpperCase()); // "JAVASCRIPT"
console.log(texto.toLowerCase()); // "javascript"
```

### 5.3: Number (Números)

Inteiros e decimais (não há diferença em JS).

```javascript
// Números inteiros
let idade = 30;
let quantidade = 100;

// Números decimais (float/double em outras linguagens)
let preco = 19.99;
let pi = 3.14159;

// Números negativos
let temperatura = -5;
let divida = -1500.50;

// Operações matemáticas básicas
let soma = 10 + 5;           // 15
let subtracao = 20 - 8;      // 12
let multiplicacao = 4 * 3;   // 12
let divisao = 15 / 3;        // 5
let resto = 10 % 3;          // 1 (módulo)
let potencia = 2 ** 3;       // 8 (2³)

// Valores especiais
let infinito = Infinity;
let naoNumero = NaN;  // Not a Number
console.log(10 / 0);         // Infinity
console.log("texto" * 2);    // NaN
```

### 5.4: Boolean (Verdadeiro/Falso)

Apenas dois valores possíveis: `true` ou `false`.

```javascript
// Valores booleanos
let maiorDeIdade = true;
let temCarteiraMotorista = false;
let estudante = true;

// Comparações retornam boolean
let dez = 10;
let cinco = 5;

console.log(dez > cinco);    // true
console.log(dez < cinco);    // false
console.log(dez === 10);     // true
console.log(cinco === 10);   // false

// Uso prático
const idadeMinima = 18;
let suaIdade = 20;
let podeVotar = suaIdade >= idadeMinima;
console.log("Pode votar?", podeVotar);  // true
```

### 5.5: Undefined

Variável declarada mas **sem valor atribuído**.

```javascript
let nome;
console.log(nome);  // undefined

let idade;
console.log(idade); // undefined

// Depois de atribuir valor
idade = 25;
console.log(idade); // 25
```

### 5.6: Null

Representa **ausência intencional** de valor.

```javascript
let usuario = null;  // Ainda não há usuário logado
console.log(usuario);  // null

// Diferença entre undefined e null
let semValor;           // undefined (não definido)
let semUsuario = null;  // null (intencionalmente vazio)
```

### 5.7: Operador typeof

Verifica o **tipo** de uma variável.

```javascript
console.log(typeof "João");        // "string"
console.log(typeof 42);            // "number"
console.log(typeof 3.14);          // "number"
console.log(typeof true);          // "boolean"
console.log(typeof undefined);     // "undefined"
console.log(typeof null);          // "object" (bug histórico!)

// Com variáveis
let nome = "Maria";
let idade = 30;
let ativo = true;

console.log(typeof nome);   // "string"
console.log(typeof idade);  // "number"
console.log(typeof ativo);  // "boolean"
```

---

## Parte 6: Conversão de Tipos (Type Coercion)

### 6.1: Conversão Implícita (Automática)

```javascript
// String + Number = String
console.log("10" + 5);      // "105" (concatenação)
console.log("Idade: " + 25); // "Idade: 25"

// Operações matemáticas convertem para number
console.log("10" - 5);      // 5 (number)
console.log("10" * 2);      // 20 (number)
console.log("10" / 2);      // 5 (number)
```

### 6.2: Conversão Explícita (Manual)

```javascript
// String para Number
let textoNumero = "42";
let numero1 = Number(textoNumero);
let numero2 = parseInt(textoNumero);
let numero3 = parseFloat("3.14");

console.log(numero1);  // 42
console.log(numero2);  // 42
console.log(numero3);  // 3.14

// Number para String
let idade = 25;
let idadeTexto1 = String(idade);
let idadeTexto2 = idade.toString();

console.log(typeof idadeTexto1);  // "string"
console.log(idadeTexto2);         // "25"

// Boolean para String/Number
let ativo = true;
console.log(String(ativo));  // "true"
console.log(Number(ativo));  // 1

let inativo = false;
console.log(Number(inativo)); // 0
```

---

## 🎓 Parte 7: Exercícios Práticos

### Exercício 1: Declaração de Variáveis ⭐

**Objetivo:** Praticar declaração de variáveis com `let` e `const`.

**Tarefa:**

1. Declare variáveis para armazenar:
   - Seu nome completo (const)
   - Sua idade (let)
   - Sua cidade (const)
   - Se você é estudante (const - boolean)
2. Exiba todas no console usando `console.log()`

**Solução esperada:**

```javascript
const nomeCompleto = "João Silva Santos";
let idade = 22;
const cidade = "São Paulo";
const estudante = true;

console.log("Nome:", nomeCompleto);
console.log("Idade:", idade);
console.log("Cidade:", cidade);
console.log("É estudante?", estudante);
```

---

### Exercício 2: Tipos de Dados ⭐

**Objetivo:** Identificar tipos de dados usando `typeof`.

**Tarefa:**

Crie 5 variáveis com tipos diferentes e use `typeof` para verificar cada uma:

```javascript
// Seu código aqui
let variavel1 = ____;
let variavel2 = ____;
// ...

console.log(typeof variavel1);
// ...
```

**Dica:** Use string, number, boolean, undefined e null.

---

### Exercício 3: Reatribuição ⭐⭐

**Objetivo:** Entender diferença entre `let` e `const`.

**Tarefa:**

```javascript
// 1. Declare uma variável com let e atribua sua idade
// 2. Exiba no console
// 3. Aumente sua idade em 1 ano
// 4. Exiba novamente

// 5. Declare uma constante com o ano atual
// 6. Tente mudar o valor (vai dar erro - OK!)
// 7. Comente a linha que dá erro
```

---

### Exercício 4: Concatenação de Strings ⭐⭐

**Objetivo:** Trabalhar com strings e concatenação.

**Tarefa:**

Crie variáveis e monte uma frase completa:

```javascript
const nome = "Ana";
const idade = 28;
const profissao = "desenvolvedora";

// Monte a frase: "Olá, meu nome é Ana, tenho 28 anos e sou desenvolvedora."
// Use duas formas: + e template literals
```

**Solução esperada:**

```javascript
// Forma 1: Concatenação com +
let frase1 = "Olá, meu nome é " + nome + ", tenho " + idade + " anos e sou " + profissao + ".";

// Forma 2: Template literals (MODERNA)
let frase2 = `Olá, meu nome é ${nome}, tenho ${idade} anos e sou ${profissao}.`;

console.log(frase1);
console.log(frase2);
```

---

### Exercício 5: Operações Matemáticas ⭐⭐

**Objetivo:** Praticar operações matemáticas básicas.

**Tarefa:**

```javascript
// Declare duas variáveis numéricas
const numero1 = 15;
const numero2 = 4;

// Calcule e exiba:
// 1. Soma
// 2. Subtração
// 3. Multiplicação
// 4. Divisão
// 5. Resto da divisão (módulo)
// 6. Potência (numero1 elevado a numero2)
```

---

### Exercício 6: Calculadora de IMC ⭐⭐⭐

**Objetivo:** Criar programa prático combinando conceitos.

**Tarefa:**

Calcule o IMC (Índice de Massa Corporal).

**Fórmula:** IMC = peso / (altura²)

```javascript
// Seus dados
const peso = 70;      // em kg
const altura = 1.75;  // em metros

// Calcule o IMC
// Exiba: "Seu IMC é: [valor]"
```

**Solução esperada:**

```javascript
const peso = 70;
const altura = 1.75;
const imc = peso / (altura ** 2);

console.log(`Seu IMC é: ${imc.toFixed(2)}`);
// Resultado: "Seu IMC é: 22.86"
```

---

### Exercício 7: Conversão de Temperaturas ⭐⭐⭐

**Objetivo:** Praticar operações e conversões.

**Tarefa:**

Converta temperatura de Celsius para Fahrenheit.

**Fórmula:** F = (C × 9/5) + 32

```javascript
const temperaturaCelsius = 25;

// Calcule a temperatura em Fahrenheit
// Exiba: "25°C equivale a [valor]°F"
```

---

### Exercício 8: Perfil Completo ⭐⭐⭐

**Objetivo:** Projeto integrador da semana.

**Tarefa:**

Crie um perfil pessoal completo com pelo menos 8 variáveis diferentes:

```javascript
// Informações pessoais
const nome = "seu nome";
let idade = 0;
// ... adicione mais variáveis

// Exiba tudo formatado
console.log("===== MEU PERFIL =====");
console.log(`Nome: ${nome}`);
// ... continue
```

**Requisitos:**

- Use pelo menos 3 `const` e 3 `let`
- Tenha pelo menos 1 boolean
- Use template literals
- Calcule algo (idade em meses, anos até aposentadoria, etc.)

---

## Parte 8: Desafios Extras (Opcional)

### Desafio 1: Troca de Variáveis 🔥

Troque os valores de duas variáveis **sem usar uma terceira variável**.

```javascript
let a = 10;
let b = 20;

// Seu código aqui (sem criar let c)

console.log(a); // deve mostrar 20
console.log(b); // deve mostrar 10
```

### Desafio 2: Números Curiosos 🔥🔥

```javascript
// Descubra o resultado ANTES de executar:
console.log(0.1 + 0.2);        // ?
console.log(typeof NaN);       // ?
console.log(typeof null);      // ?
console.log(10 / 0);           // ?
console.log("5" - 3);          // ?
console.log("5" + 3);          // ?
```

### Desafio 3: Projeto Mini-Loja 🔥🔥🔥

```javascript
// Dados da loja
const nomeProduto = "Notebook";
const precoProduto = 2500.00;
let quantidadeEstoque = 10;
const descontoPercentual = 15;

// Calcule:
// 1. Valor do desconto em reais
// 2. Preço final com desconto
// 3. Simule venda de 3 unidades (atualize estoque)
// 4. Valor total da venda (com desconto)

// Exiba tudo formatado
```

---

## Parte 9: Checklist de Aprendizado

Ao final da Semana 1, você deve ser capaz de:

- [ ] Explicar o que é JavaScript e onde é usado
- [ ] Abrir e usar o Console do navegador
- [ ] Criar arquivo HTML com JavaScript externo
- [ ] Usar `console.log()` para exibir informações
- [ ] Declarar variáveis com `let` e `const`
- [ ] Explicar a diferença entre `let` e `const`
- [ ] Nomear variáveis seguindo convenções
- [ ] Identificar os 5 tipos primitivos principais
- [ ] Usar o operador `typeof`
- [ ] Concatenar strings com `+` e template literals
- [ ] Realizar operações matemáticas básicas
- [ ] Converter entre tipos de dados
- [ ] Criar programas simples combinando conceitos

---

## Parte 10: Troubleshooting (Problemas Comuns)

### Problema 1: "Uncaught ReferenceError: x is not defined"

**Causa:** Variável não foi declarada ou há erro de digitação.

```javascript
console.log(nome);  // ❌ Erro se 'nome' não existe

const nome = "João";
console.log(nome);  // ✅ Funciona
```

### Problema 2: "Uncaught TypeError: Assignment to constant variable"

**Causa:** Tentou reatribuir valor a uma `const`.

```javascript
const idade = 25;
idade = 26;  // ❌ ERRO!

// Solução: use let
let idade = 25;
idade = 26;  // ✅ Funciona
```

### Problema 3: Console não exibe nada

**Verificar:**

1. JavaScript está sendo carregado? (veja aba Network no DevTools)
2. Há erros no console? (ícone vermelho)
3. Script está no final do `<body>`?

### Problema 4: Cálculos estranhos

```javascript
console.log(0.1 + 0.2);  // 0.30000000000000004

// Solução: use toFixed()
let resultado = (0.1 + 0.2).toFixed(2);
console.log(resultado);  // "0.30"
```

---

## Parte 11: Recursos para Estudo

### Documentação Oficial

- **MDN Web Docs**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript
- **JavaScript.info**: https://javascript.info/

### Ferramentas Online para Prática

- **JSFiddle**: https://jsfiddle.net/
- **CodePen**: https://codepen.io/
- **JS Bin**: https://jsbin.com/

### Extensões VS Code Recomendadas

- **Live Server**: Atualização automática
- **JavaScript (ES6) code snippets**: Atalhos úteis
- **Bracket Pair Colorizer**: Colorir chaves

---

## Parte 12: Dicas de Ouro para Iniciantes

### ✅ FAÇA:

1. **Digite o código manualmente** - não copie e cole
2. **Experimente variações** - mude valores e veja o que acontece
3. **Use nomes descritivos** - `nomeUsuario` é melhor que `x`
4. **Comente seu código** - explique o que faz
5. **Teste frequentemente** - use `console.log()` para debugar
6. **Leia mensagens de erro** - elas te ajudam a aprender

### ❌ EVITE:

1. Decorar código sem entender
2. Pular exercícios
3. Usar `var` (use `let` e `const`)
4. Nomes de variáveis sem significado (`a`, `b`, `x`)
5. Copiar código sem testar
6. Desistir no primeiro erro

---

## Parte 13: Preparação para Semana 2

Na próxima semana você aprenderá:

- ✨ Operadores aritméticos avançados
- ✨ Operadores de comparação (`==` vs `===`)
- ✨ Operadores lógicos (AND, OR, NOT)
- ✨ Precedência de operadores
- ✨ Expressões complexas

**Pré-requisito:** Domine bem os conceitos desta semana!

---

## Projeto de Conclusão da Semana 1

### 🎯 Desafio Final: Cartão de Visita Digital

**Objetivo:** Criar um programa que exibe suas informações profissionais.

**Requisitos mínimos:**

```javascript
// 1. DADOS PESSOAIS (use const)
const nome = "";
const profissao = "";
const empresa = "";
const email = "";
const telefone = "";

// 2. DADOS PROFISSIONAIS (use let se pode mudar)
let anosExperiencia = 0;
let linguagensProgramacao = 3;  // quantidade

// 3. CÁLCULOS
const anoAtual = 2025;
// Calcule ano que começou a trabalhar

// 4. EXIBIÇÃO
console.log("========================================");
console.log("       CARTÃO DE VISITA DIGITAL        ");
console.log("========================================");
// Use template literals para exibir tudo formatado
console.log(`Nome: ${nome}`);
// ... continue

// 5. ESTATÍSTICAS
// Calcule e exiba:
// - Meses de experiência
// - Média de linguagens por ano
```

**Critérios de avaliação:**

- [ ] Usa pelo menos 5 `const` e 2 `let`
- [ ] Tem pelo menos 3 tipos de dados diferentes
- [ ] Faz pelo menos 2 cálculos
- [ ] Usa template literals
- [ ] Código comentado e organizado
- [ ] Exibição formatada e bonita

---

## Considerações Finais

### 🎉 Parabéns por completar a Semana 1!

Você deu o primeiro passo importante na jornada JavaScript. Os conceitos desta semana são a **base de tudo** que virá a seguir.

### 📚 Antes de avançar, certifique-se de:

1. Entender completamente `let` vs `const`
2. Dominar os 5 tipos primitivos
3. Conseguir criar variáveis e exibir valores
4. Fazer operações matemáticas básicas
5. Trabalhar com strings e concatenação

### 💡 Lembre-se:

> "A prática leva à perfeição. Não tenha medo de errar, os erros são seus melhores professores!"

---

**Professor:** 

**Curso:** Introdução ao JavaScript

**Semana:** 1 de 8

**Próxima aula:** Operadores e Expressões

---

**Dúvidas?** Revise os conceitos e refaça os exercícios.

**Bons estudos! 🚀**