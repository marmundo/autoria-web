# Roteiro de Estudos: Introdução ao JavaScript - Semana 2

## Objetivo da Semana

Dominar os operadores do JavaScript, compreender como funcionam as comparações e expressões lógicas, e aplicar esses conhecimentos na resolução de problemas práticos do dia a dia.

---

## ⚠️ PRÉ-REQUISITOS OBRIGATÓRIOS

**ATENÇÃO:** Antes de iniciar esta semana, você DEVE dominar:

- ✅ Declaração de variáveis (`let` e `const`)
- ✅ Tipos de dados primitivos (string, number, boolean)
- ✅ Uso do `console.log()`
- ✅ Concatenação básica de strings

**Se ainda tem dúvidas:** Revise a Semana 1 antes de prosseguir!

---

## Parte 1: Operadores Aritméticos

### 1.1: Operadores Básicos

Os operadores aritméticos realizam cálculos matemáticos.

```javascript
// ADIÇÃO (+)
let soma = 10 + 5;
console.log(soma);  // 15

let preco1 = 50.00;
let preco2 = 30.50;
let total = preco1 + preco2;
console.log("Total:", total);  // 80.50

// SUBTRAÇÃO (-)
let estoque = 100;
let vendidos = 23;
let restante = estoque - vendidos;
console.log("Restante:", restante);  // 77

// MULTIPLICAÇÃO (*)
let precoUnitario = 25.00;
let quantidade = 4;
let valorTotal = precoUnitario * quantidade;
console.log("Valor total:", valorTotal);  // 100.00

// DIVISÃO (/)
let totalPontos = 450;
let numeroJogos = 15;
let mediaPorJogo = totalPontos / numeroJogos;
console.log("Média:", mediaPorJogo);  // 30
```

### 1.2: Operadores Especiais

#### A) Módulo (%) - Resto da Divisão

Retorna o **resto** da divisão entre dois números.

```javascript
// Exemplos básicos
console.log(10 % 3);   // 1 (10 ÷ 3 = 3, resto 1)
console.log(15 % 4);   // 3 (15 ÷ 4 = 3, resto 3)
console.log(20 % 5);   // 0 (divisão exata)

// USO PRÁTICO 1: Verificar número par ou ímpar
let numero = 7;
let restoDivisao = numero % 2;
console.log(restoDivisao);  // 1 (ímpar)

numero = 8;
restoDivisao = numero % 2;
console.log(restoDivisao);  // 0 (par)

// USO PRÁTICO 2: Verificar múltiplos
let numero1 = 15;
console.log(numero1 % 5);  // 0 (15 é múltiplo de 5)

let numero2 = 17;
console.log(numero2 % 5);  // 2 (17 NÃO é múltiplo de 5)

// USO PRÁTICO 3: Pegar último dígito
let numero3 = 12345;
let ultimoDigito = numero3 % 10;
console.log(ultimoDigito);  // 5
```

#### B) Exponenciação (**) - Potência

Eleva um número a uma potência.

```javascript
// Sintaxe: base ** expoente

console.log(2 ** 3);    // 8 (2³ = 2 × 2 × 2)
console.log(5 ** 2);    // 25 (5² = 5 × 5)
console.log(10 ** 3);   // 1000 (10³)
console.log(3 ** 4);    // 81 (3⁴)

// Uso prático: Cálculo de juros compostos
const capital = 1000;
const taxa = 1.05;  // 5% ao mês
const meses = 12;
const montante = capital * (taxa ** meses);
console.log(`Montante após ${meses} meses: R$ ${montante.toFixed(2)}`);

// Raiz quadrada (expoente 0.5)
console.log(9 ** 0.5);   // 3 (√9)
console.log(16 ** 0.5);  // 4 (√16)
```

### 1.3: Incremento e Decremento

Operadores especiais para aumentar ou diminuir valores em 1.

```javascript
// INCREMENTO (++)
let contador = 0;

contador++;  // contador = contador + 1
console.log(contador);  // 1

contador++;
console.log(contador);  // 2

// Equivalente a:
contador = contador + 1;

// DECREMENTO (--)
let vidas = 3;

vidas--;  // vidas = vidas - 1
console.log(vidas);  // 2

vidas--;
console.log(vidas);  // 1

// PRÉ vs PÓS incremento
let x = 5;

// Pós-incremento (usa DEPOIS)
let y = x++;  
console.log(y);  // 5 (valor antigo)
console.log(x);  // 6 (incrementou depois)

// Pré-incremento (usa ANTES)
let a = 5;
let b = ++a;
console.log(b);  // 6 (incrementou antes)
console.log(a);  // 6

// EXEMPLO PRÁTICO: Sistema de pontuação
let pontos = 0;
console.log("Pontos iniciais:", pontos);

pontos += 10;  // Acertou primeira questão
console.log("Após acerto:", pontos);  // 10

pontos += 15;  // Acertou segunda questão
console.log("Após segundo acerto:", pontos);  // 25

pontos -= 5;  // Erro na terceira
console.log("Após erro:", pontos);  // 20
```

### 1.4: Operadores de Atribuição Compostos

Atalhos para operações comuns.

```javascript
// Atribuição simples
let numero = 10;

// ADIÇÃO COMPOSTA (+=)
numero += 5;  // Equivale a: numero = numero + 5
console.log(numero);  // 15

// SUBTRAÇÃO COMPOSTA (-=)
numero -= 3;  // numero = numero - 3
console.log(numero);  // 12

// MULTIPLICAÇÃO COMPOSTA (*=)
numero *= 2;  // numero = numero * 2
console.log(numero);  // 24

// DIVISÃO COMPOSTA (/=)
numero /= 4;  // numero = numero / 4
console.log(numero);  // 6

// MÓDULO COMPOSTO (%=)
numero %= 4;  // numero = numero % 4
console.log(numero);  // 2

// EXPONENCIAÇÃO COMPOSTA (**=)
numero **= 3;  // numero = numero ** 3
console.log(numero);  // 8

// EXEMPLO PRÁTICO: Carrinho de compras
let totalCarrinho = 0;

totalCarrinho += 50.00;   // Adiciona produto 1
totalCarrinho += 30.00;   // Adiciona produto 2
totalCarrinho += 20.00;   // Adiciona produto 3
console.log("Subtotal:", totalCarrinho);  // 100.00

totalCarrinho -= 10.00;   // Remove um produto
console.log("Após remoção:", totalCarrinho);  // 90.00

totalCarrinho *= 0.9;     // Aplica desconto de 10%
console.log("Com desconto:", totalCarrinho.toFixed(2));  // 81.00
```

### 1.5: Precedência de Operadores

Ordem em que as operações são executadas.

```javascript
// Sem parênteses - ordem matemática padrão
let resultado1 = 10 + 5 * 2;
console.log(resultado1);  // 20 (multiplica primeiro: 5*2=10, depois soma 10+10)

// Com parênteses - força ordem diferente
let resultado2 = (10 + 5) * 2;
console.log(resultado2);  // 30 (soma primeiro: 10+5=15, depois multiplica 15*2)

// Ordem de precedência (maior para menor):
// 1. ()         Parênteses
// 2. **         Exponenciação
// 3. *, /, %    Multiplicação, Divisão, Módulo
// 4. +, -       Adição, Subtração

// Exemplos práticos
console.log(2 + 3 * 4);        // 14 (não 20)
console.log((2 + 3) * 4);      // 20
console.log(10 - 2 * 3);       // 4 (não 24)
console.log((10 - 2) * 3);     // 24
console.log(2 ** 3 + 1);       // 9 (potência primeiro)
console.log(2 ** (3 + 1));     // 16

// Cálculo complexo: Média ponderada
let nota1 = 8;
let nota2 = 7;
let nota3 = 9;
let peso1 = 2;
let peso2 = 3;
let peso3 = 5;

let mediaPonderada = (nota1 * peso1 + nota2 * peso2 + nota3 * peso3) / (peso1 + peso2 + peso3);
console.log("Média ponderada:", mediaPonderada.toFixed(2));  // 8.10
```

---

## Parte 2: Operadores de Comparação

### 2.1: Operadores Básicos de Comparação

Operadores de comparação **sempre retornam boolean** (true ou false).

```javascript
// MAIOR QUE (>)
console.log(10 > 5);      // true
console.log(3 > 8);       // false
console.log(5 > 5);       // false

// MENOR QUE (<)
console.log(3 < 7);       // true
console.log(10 < 2);      // false
console.log(5 < 5);       // false

// MAIOR OU IGUAL (>=)
console.log(10 >= 5);     // true
console.log(5 >= 5);      // true ✅ (igual conta!)
console.log(3 >= 8);      // false

// MENOR OU IGUAL (<=)
console.log(3 <= 7);      // true
console.log(5 <= 5);      // true ✅ (igual conta!)
console.log(10 <= 2);     // false

// Exemplos práticos
const idadeMinima = 18;
const suaIdade = 20;

let podeVotar = suaIdade >= idadeMinima;
console.log("Pode votar?", podeVotar);  // true

const notaMinima = 7;
const suaNota = 6.5;

let aprovado = suaNota >= notaMinima;
console.log("Aprovado?", aprovado);  // false
```

### 2.2: Igualdade - O Grande Mistério (== vs ===)

**ATENÇÃO:** Esta é uma das partes mais importantes do JavaScript!

#### A) Igualdade Frouxa (==) - Compara APENAS o valor

```javascript
// Comparações que parecem estranhas com ==
console.log(5 == 5);        // true (óbvio)
console.log(5 == "5");      // true ⚠️ (converte string para número)
console.log(1 == true);     // true ⚠️ (true vira 1)
console.log(0 == false);    // true ⚠️ (false vira 0)
console.log(null == undefined);  // true ⚠️

// Conversões implícitas (coerção de tipo)
console.log("10" == 10);    // true (string "10" → número 10)
console.log(" " == 0);      // true (string vazia → 0)
console.log("0" == 0);      // true
```

#### B) Igualdade Estrita (===) - Compara valor E tipo

```javascript
// SEMPRE use === no JavaScript moderno!

console.log(5 === 5);       // true
console.log(5 === "5");     // false ✅ (tipos diferentes)
console.log(1 === true);    // false ✅
console.log(0 === false);   // false ✅
console.log(null === undefined);  // false ✅

// Exemplos práticos
let numero = 10;
let texto = "10";

console.log(numero == texto);   // true (evite!)
console.log(numero === texto);  // false (correto!)

// Comparação segura
let idade = 18;

// ❌ MAL (pode dar problemas)
if (idade == "18") {
    console.log("Maior de idade");
}

// ✅ BOM (recomendado)
if (idade === 18) {
    console.log("Maior de idade");
}
```

### 2.3: Desigualdade (!= vs !==)

```javascript
// Desigualdade frouxa (!=)
console.log(5 != 3);        // true
console.log(5 != "5");      // false ⚠️ (converte)
console.log(1 != true);     // false ⚠️

// Desigualdade estrita (!==) - RECOMENDADO
console.log(5 !== 3);       // true
console.log(5 !== "5");     // true ✅ (tipos diferentes)
console.log(1 !== true);    // true ✅

// Exemplo prático
let statusPedido = "pendente";

// ❌ Evite
if (statusPedido != "entregue") {
    console.log("Pedido não foi entregue");
}

// ✅ Prefira
if (statusPedido !== "entregue") {
    console.log("Pedido não foi entregue");
}
```

### 2.4: Tabela Comparativa Completa

```javascript
// Comparação de valores
console.log("=== NÚMEROS ===");
console.log(10 === 10);      // true
console.log(10 === 5);       // false
console.log(10 !== 5);       // true

console.log("\n=== STRINGS ===");
console.log("hello" === "hello");    // true
console.log("hello" === "Hello");    // false (case-sensitive!)
console.log("10" === "10");          // true

console.log("\n=== TIPOS DIFERENTES ===");
console.log(10 === "10");    // false
console.log(true === 1);     // false
console.log(false === 0);    // false
console.log(null === undefined);  // false

console.log("\n=== BOOLEAN ===");
console.log(true === true);   // true
console.log(true !== false);  // true
```

### 2.5: Casos Especiais - NaN e null

```javascript
// NaN (Not a Number) é especial
let resultado = "texto" * 2;
console.log(resultado);           // NaN
console.log(resultado === NaN);   // false ⚠️ (NaN não é igual a nada!)
console.log(isNaN(resultado));    // true ✅ (forma correta)

// null e undefined
console.log(null === null);           // true
console.log(undefined === undefined); // true
console.log(null === undefined);      // false
console.log(null == undefined);       // true ⚠️

// Verificando se variável está vazia
let usuario;
console.log(usuario === undefined);  // true

let dadosUsuario = null;
console.log(dadosUsuario === null);  // true
```

---

## Parte 3: Operadores Lógicos

### 3.1: Operador AND (&&) - E Lógico

Retorna `true` APENAS se **TODAS** as condições forem verdadeiras.

```javascript
// Tabela verdade AND
console.log(true && true);    // true
console.log(true && false);   // false
console.log(false && true);   // false
console.log(false && false);  // false

// Exemplos práticos
let maiorDeIdade = true;
let temCarteiraMotorista = true;
let podeDirigir = maiorDeIdade && temCarteiraMotorista;
console.log("Pode dirigir?", podeDirigir);  // true

// Se uma condição é falsa, resultado é false
let temIdade = true;
let temCarteira = false;
let podeDirigir2 = temIdade && temCarteira;
console.log("Pode dirigir?", podeDirigir2);  // false

// Múltiplas condições
let idade = 25;
let temCNH = true;
let temCarro = true;

let podeViajar = idade >= 18 && temCNH && temCarro;
console.log("Pode viajar?", podeViajar);  // true

// Exemplo realista: Sistema de login
let usuarioCorreto = "admin";
let senhaCorreta = "1234";

let usuarioDigitado = "admin";
let senhaDigitada = "1234";

let loginSucesso = usuarioDigitado === usuarioCorreto && senhaDigitada === senhaCorreta;
console.log("Login autorizado?", loginSucesso);  // true
```

### 3.2: Operador OR (||) - OU Lógico

Retorna `true` se **PELO MENOS UMA** condição for verdadeira.

```javascript
// Tabela verdade OR
console.log(true || true);    // true
console.log(true || false);   // true
console.log(false || true);   // true
console.log(false || false);  // false ← única forma de ser false

// Exemplos práticos
let temDinheiro = false;
let temCartao = true;
let podePagar = temDinheiro || temCartao;
console.log("Pode pagar?", podePagar);  // true

// Acesso liberado se for admin OU moderador
let isAdmin = false;
let isModerador = true;
let temAcesso = isAdmin || isModerador;
console.log("Tem acesso?", temAcesso);  // true

// Sistema de descontos
let idadeDesconto = 17;  // menor de 18 ou maior de 60 tem desconto
let temDescontoIdade = idadeDesconto < 18 || idadeDesconto > 60;
console.log("Tem desconto por idade?", temDescontoIdade);  // true

// Exemplo realista: Validação de formulário
let emailPreenchido = true;
let telefonePreenchido = false;
let temContato = emailPreenchido || telefonePreenchido;
console.log("Tem pelo menos um contato?", temContato);  // true
```

### 3.3: Operador NOT (!) - Negação

Inverte o valor booleano.

```javascript
// Negação simples
console.log(!true);   // false
console.log(!false);  // true

// Dupla negação (volta ao original)
console.log(!!true);   // true
console.log(!!false);  // false

// Exemplos práticos
let chovendo = true;
let solEnsolarado = !chovendo;
console.log("Está ensolarado?", solEnsolarado);  // false

// Negando comparações
let idade = 16;
let menorDeIdade = idade < 18;
let maiorDeIdade = !menorDeIdade;
console.log("Maior de idade?", maiorDeIdade);  // false

// Negação com ===
let usuarioLogado = false;
if (!usuarioLogado) {
    console.log("Usuário NÃO está logado");
}

// Exemplo: Sistema de permissões
let isAdministrador = false;
let acessoNegado = !isAdministrador;
console.log("Acesso negado?", acessoNegado);  // true

// Valores "truthy" e "falsy"
console.log(!0);        // true (0 é falsy)
console.log(!"");       // true (string vazia é falsy)
console.log(!null);     // true (null é falsy)
console.log(!undefined);// true (undefined é falsy)
console.log(!"texto");  // false (string preenchida é truthy)
console.log(!42);       // false (números diferentes de 0 são truthy)
```

### 3.4: Combinando Operadores Lógicos

```javascript
// AND + OR
let idade = 25;
let temCarteira = true;
let temCarro = false;

// Pode dirigir SE (maior de 18 E tem carteira) OU (tem carro do amigo)
let podeDirigir = (idade >= 18 && temCarteira) || temCarro;
console.log(podeDirigir);  // true

// Precedência: ! > && > ||
// Sempre use parênteses para clareza!

let a = true;
let b = false;
let c = true;

let resultado1 = a || b && c;  // true (b && c primeiro)
let resultado2 = (a || b) && c;  // true (a || b primeiro)

console.log(resultado1);
console.log(resultado2);

// Exemplo complexo: Sistema de promoções
let clienteVIP = true;
let compraAcimaDe100 = false;
let primeiraCompra = false;
let diaAniversario = true;

// Ganha desconto se:
// (É VIP OU compra > 100) E (primeira compra OU aniversário)
let ganhaDesconto = (clienteVIP || compraAcimaDe100) && (primeiraCompra || diaAniversario);
console.log("Ganha desconto?", ganhaDesconto);  // true
```

### 3.5: Curto-Circuito (Short-Circuit)

JavaScript otimiza operações lógicas.

```javascript
// AND (&&) - para na primeira false
console.log(false && console.log("Não executa"));  // não imprime
console.log(true && console.log("Executa!"));      // imprime "Executa!"

// OR (||) - para na primeira true
console.log(true || console.log("Não executa"));   // não imprime
console.log(false || console.log("Executa!"));     // imprime "Executa!"

// Uso prático: Valores padrão
let nomeUsuario = "";
let nomeExibicao = nomeUsuario || "Visitante";
console.log(nomeExibicao);  // "Visitante"

nomeUsuario = "João";
nomeExibicao = nomeUsuario || "Visitante";
console.log(nomeExibicao);  // "João"

// Verificação segura de propriedades
let usuario = null;
let email = usuario && usuario.email;  // undefined (não dá erro!)
console.log(email);
```

---

## 🎓 Parte 4: Exercícios Práticos

### Exercício 1: Calculadora Básica ⭐

**Objetivo:** Praticar operadores aritméticos.

**Tarefa:**

```javascript
const numero1 = 15;
const numero2 = 4;

// Calcule e exiba:
// 1. Soma
// 2. Subtração
// 3. Multiplicação
// 4. Divisão
// 5. Resto (módulo)
// 6. numero1 elevado a numero2

// Formato: "15 + 4 = 19"
```

**Solução esperada:**

```javascript
const numero1 = 15;
const numero2 = 4;

console.log(`${numero1} + ${numero2} = ${numero1 + numero2}`);
console.log(`${numero1} - ${numero2} = ${numero1 - numero2}`);
console.log(`${numero1} * ${numero2} = ${numero1 * numero2}`);
console.log(`${numero1} / ${numero2} = ${numero1 / numero2}`);
console.log(`${numero1} % ${numero2} = ${numero1 % numero2}`);
console.log(`${numero1} ** ${numero2} = ${numero1 ** numero2}`);
```

---

### Exercício 2: Par ou Ímpar ⭐

**Objetivo:** Usar operador módulo (%).

**Tarefa:**

```javascript
const numero = 17;

// Use o operador % para descobrir se é par ou ímpar
// Dica: número par % 2 === 0
// Armazene o resultado em uma variável boolean
// Exiba: "O número 17 é par? false"
```

---

### Exercício 3: Comparações ⭐⭐

**Objetivo:** Praticar == vs ===.

**Tarefa:**

```javascript
// Compare os seguintes valores com == e ===
// Anote os resultados e explique a diferença

console.log(5 == "5");
console.log(5 === "5");

console.log(true == 1);
console.log(true === 1);

console.log(null == undefined);
console.log(null === undefined);

// Qual você deve usar e por quê?
```

---

### Exercício 4: Verificador de Idade ⭐⭐

**Objetivo:** Praticar operadores de comparação.

**Tarefa:**

```javascript
const idade = 20;

// Crie variáveis boolean para:
const ehMaiorDeIdade = // idade >= 18
const ehIdoso = // idade >= 60
const ehMenor = // idade < 18
const podeVotar = // idade >= 16
const podeTomarCerveja = // idade >= 18

// Exiba todas as informações
console.log("Maior de idade?", ehMaiorDeIdade);
// ... continue
```

---

### Exercício 5: Sistema de Login ⭐⭐

**Objetivo:** Usar operador AND (&&).

**Tarefa:**

```javascript
// Dados corretos do sistema
const usuarioCorreto = "admin";
const senhaCorreta = "12345";

// Dados digitados pelo usuário
const usuarioDigitado = "admin";
const senhaDigitada = "12345";

// Verifique se AMBOS estão corretos
const loginAutorizado = // seu código aqui

console.log("Login autorizado?", loginAutorizado);

// Teste com valores diferentes também!
```

---

### Exercício 6: Sistema de Descontos ⭐⭐⭐

**Objetivo:** Combinar operadores lógicos.

**Tarefa:**

```javascript
const idade = 17;
const ehEstudante = true;
const ehPrimeiraCompra = false;

// Regras de desconto:
// - Menores de 18 OU maiores de 60 (desconto por idade)
// - É estudante E primeira compra (desconto estudante)
// Ganha desconto se ALGUMA das regras for verdadeira

const temDescontoIdade = // idade < 18 || idade > 60
const temDescontoEstudante = // ehEstudante && ehPrimeiraCompra
const ganhaDesconto = // temDescontoIdade || temDescontoEstudante

console.log("Ganha desconto?", ganhaDesconto);
```

---

### Exercício 7: Validador de Senha ⭐⭐⭐

**Objetivo:** Validar múltiplas condições.

**Tarefa:**

```javascript
const senha = "abc12345";

// Senha válida se:
// - Tamanho >= 8 caracteres
// - Contém números (você pode supor que contém)

const tamanhoValido = senha.length >= 8;
const contemNumeros = true;  // vamos assumir
const senhaValida = // ambas as condições verdadeiras

console.log("Tamanho:", senha.length);
console.log("Tamanho válido?", tamanhoValido);
console.log("Contém números?", contemNumeros);
console.log("Senha válida?", senhaValida);
```

---

### Exercício 8: Calculadora de Média ⭐⭐⭐

**Objetivo:** Combinar operadores aritméticos e comparação.

**Tarefa:**

```javascript
const nota1 = 7.5;
const nota2 = 8.0;
const nota3 = 6.5;

// Calcule a média
const media = // (nota1 + nota2 + nota3) / 3

// Verifique se foi aprovado (média >= 7)
const aprovado = // seu código aqui

console.log("Nota 1:", nota1);
console.log("Nota 2:", nota2);
console.log("Nota 3:", nota3);
console.log("Média:", media.toFixed(2));
console.log("Aprovado?", aprovado);
```

---

### Exercício 9: Conversor de Temperatura ⭐⭐⭐

**Objetivo:** Aplicar fórmulas matemáticas.

**Tarefa:**

```javascript
const celsius = 25;

// Converta para Fahrenheit: F = C * 9/5 + 32
const fahrenheit = // seu código aqui

// Converta para Kelvin: K = C + 273.15
const kelvin = // seu código aqui

console.log(`${celsius}°C equivale a:`);
console.log(`${fahrenheit.toFixed(2)}°F`);
console.log(`${kelvin.toFixed(2)}K`);
```

---

### Exercício 10: Sistema de Pontuação ⭐⭐⭐

**Objetivo:** Usar operadores compostos.

**Tarefa:**

```javascript
let pontos = 0;
console.log("Pontos iniciais:", pontos);

// Acertou questão 1 (vale 10 pontos)
pontos += 10;
console.log("Após questão 1:", pontos);

// Acertou questão 2 (vale 15 pontos)
// Seu código aqui

// Errou questão 3 (perde 5 pontos)
// Seu código aqui

// Bônus: dobrar pontos
// Seu código aqui

// Exibir pontuação final
```

---

## Parte 5: Desafios Avançados (Opcional)

### Desafio 1: Verificador de Triângulo 🔥🔥

Três lados formam um triângulo válido se:
- Soma de dois lados > terceiro lado (para todas as combinações)

```javascript
const lado1 = 5;
const lado2 = 7;
const lado3 = 10;

// Verifique as três condições
const condicao1 = lado1 + lado2 > lado3;
const condicao2 = // complete
const condicao3 = // complete

const ehTrianguloValido = // todas as condições verdadeiras

console.log("É triângulo válido?", ehTrianguloValido);
```

---

### Desafio 2: Calculadora de Gorjeta 🔥🔥

```javascript
const valorConta = 150.00;

// Regras de gorjeta:
// - Se conta < 50: 20% de gorjeta
// - Se conta entre 50 e 200: 15% de gorjeta
// - Se conta > 200: 10% de gorjeta

// Dica: use comparações para determinar a porcentagem
// Depois calcule o valor da gorjeta
// E o total a pagar

const ehBaixo = valorConta < 50;
const ehMedio = valorConta >= 50 && valorConta <= 200;
const ehAlto = valorConta > 200;

// Continue o código...
```

---

### Desafio 3: Ano Bissexto 🔥🔥🔥

Um ano é bissexto se:
- É divisível por 4 E não é divisível por 100
- OU é divisível por 400

```javascript
const ano = 2024;

// Use o operador % para verificar divisibilidade
const divisivelPor4 = ano % 4 === 0;
const divisivelPor100 = // complete
const divisivelPor400 = // complete

const ehBissexto = // aplique a lógica descrita acima

console.log(`${ano} é bissexto?`, ehBissexto);
```

---

### Desafio 4: Calculadora de IMC Completa 🔥🔥🔥

```javascript
const peso = 70;      // kg
const altura = 1.75;  // metros

// 1. Calcule o IMC
const imc = peso / (altura ** 2);

// 2. Crie variáveis boolean para cada categoria:
const abaixoDoPeso = imc < 18.5;
const pesoNormal = imc >= 18.5 && imc < 25;
const sobrepeso = imc >= 25 && imc < 30;
const obesidade = imc >= 30;

// 3. Exiba tudo formatado
console.log("=== CALCULADORA DE IMC ===");
console.log(`Peso: ${peso} kg`);
console.log(`Altura: ${altura} m`);
console.log(`IMC: ${imc.toFixed(2)}`);
console.log("\n=== CLASSIFICAÇÃO ===");
console.log("Abaixo do peso?", abaixoDoPeso);
console.log("Peso normal?", pesoNormal);
console.log("Sobrepeso?", sobrepeso);
console.log("Obesidade?", obesidade);
```

---

## Parte 6: Projeto da Semana

### 🎯 Sistema de Avaliação de Elegibilidade para Empréstimo

**Objetivo:** Criar um sistema que avalia se uma pessoa pode obter empréstimo bancário.

**Requisitos:**

```javascript
// DADOS DO SOLICITANTE
const nome = "João Silva";
const idade = 28;
const rendaMensal = 3500.00;
const temEmprego = true;
const temRestricaoCPF = false;
const valorEmprestimo = 15000.00;
const parcelas = 24;

// REGRAS DO BANCO
const idadeMinima = 18;
const idadeMaxima = 70;
const rendaMinima = 2000.00;

// PARTE 1: VERIFICAÇÕES BÁSICAS
// 1.1 Idade está entre mínima e máxima?
const idadeValida = // seu código

// 1.2 Renda é suficiente?
const rendaValida = // seu código

// 1.3 Tem emprego E não tem restrição?
const situacaoCadastralOK = // seu código

// 1.4 É elegível? (todas as condições acima OK)
const ehElegivel = // seu código

// PARTE 2: CÁLCULOS FINANCEIROS
// 2.1 Valor da parcela
const valorParcela = valorEmprestimo / parcelas;

// 2.2 Parcela não pode ser > 30% da renda
const parcelaMaxima = rendaMensal * 0.30;
const parcelaEhViavel = valorParcela <= parcelaMaxima;

// 2.3 Aprovação final
const emprestimoAprovado = ehElegivel && parcelaEhViavel;

// PARTE 3: RELATÓRIO
console.log("========================================");
console.log("   ANÁLISE DE CRÉDITO - " + nome);
console.log("========================================");
console.log("\n--- DADOS DO SOLICITANTE ---");
console.log("Idade:", idade, "anos");
console.log("Renda mensal: R$", rendaMensal.toFixed(2));
console.log("Possui emprego?", temEmprego);
console.log("Restrição no CPF?", temRestricaoCPF);

console.log("\n--- DADOS DO EMPRÉSTIMO ---");
console.log("Valor solicitado: R$", valorEmprestimo.toFixed(2));
console.log("Parcelas:", parcelas + "x");
console.log("Valor da parcela: R$", valorParcela.toFixed(2));

console.log("\n--- ANÁLISE ---");
console.log("Idade válida?", idadeValida);
console.log("Renda válida?", rendaValida);
console.log("Situação cadastral OK?", situacaoCadastralOK);
console.log("Parcela viável?", parcelaEhViavel);
console.log("  (máximo 30% da renda: R$", parcelaMaxima.toFixed(2) + ")");

console.log("\n========================================");
console.log("RESULTADO:", emprestimoAprovado ? "APROVADO ✓" : "NEGADO ✗");
console.log("========================================");
```

**Critérios de avaliação:**

- [ ] Todas as verificações implementadas corretamente
- [ ] Usa operadores de comparação apropriados
- [ ] Combina operadores lógicos (&&, ||)
- [ ] Cálculos matemáticos corretos
- [ ] Código bem comentado
- [ ] Saída formatada e clara

**Desafio extra:** Adicione mais regras (tempo de emprego mínimo, score de crédito, etc.)

---

## Parte 7: Checklist de Aprendizado

Ao final da Semana 2, você deve ser capaz de:

- [ ] Usar todos os operadores aritméticos (+, -, *, /, %, **)
- [ ] Aplicar operadores de atribuição composta (+=, -=, etc.)
- [ ] Entender precedência de operadores
- [ ] Diferenciar == de === (e SEMPRE usar ===)
- [ ] Usar operadores de comparação (<, >, <=, >=)
- [ ] Explicar a tabela verdade de AND (&&)
- [ ] Explicar a tabela verdade de OR (||)
- [ ] Usar operador de negação (!)
- [ ] Combinar múltiplos operadores lógicos
- [ ] Resolver problemas lógicos complexos
- [ ] Criar expressões com parênteses
- [ ] Validar condições múltiplas

---

## Parte 8: Troubleshooting

### Problema 1: Resultado inesperado em comparação

```javascript
console.log(5 == "5");  // true ⚠️

// Solução: SEMPRE use ===
console.log(5 === "5"); // false ✅
```

### Problema 2: Precedência incorreta

```javascript
let resultado = 10 + 5 * 2;  // 20 (não 30)

// Solução: use parênteses
let resultado = (10 + 5) * 2;  // 30
```

### Problema 3: Divisão por zero

```javascript
console.log(10 / 0);  // Infinity

// Solução: verifique antes
let divisor = 0;
if (divisor !== 0) {
    console.log(10 / divisor);
} else {
    console.log("Não é possível dividir por zero");
}
```

### Problema 4: Comparação com NaN

```javascript
let x = "texto" * 2;  // NaN
console.log(x === NaN);  // false ⚠️

// Solução: use isNaN()
console.log(isNaN(x));  // true ✅
```

---

## Parte 9: Dicas de Ouro

### ✅ BOAS PRÁTICAS:

1. **SEMPRE use ===** em vez de ==
2. **Use parênteses** para clareza em expressões complexas
3. **Quebre expressões longas** em variáveis intermediárias
4. **Nomeie bem** variáveis booleanas (isAdmin, temPermissao)
5. **Teste todos os casos** (true/false, limites, zeros)

### ❌ EVITE:

1. Usar == (exceto em casos muito específicos)
2. Expressões longas sem parênteses
3. Lógica complexa em uma linha só
4. Comparar diretamente com NaN
5. Esquecer precedência de operadores

---

## Recursos Adicionais

### Documentação:
- **MDN - Operadores**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Expressions_and_Operators
- **JavaScript.info - Operadores**: https://javascript.info/operators

### Ferramentas Online:
- **Visualizador de Lógica**: truthtable.io
- **JS Playground**: jsbin.com

---

## Preparação para Semana 3

Na próxima semana você aprenderá:
- ✨ Estruturas condicionais (if, else if, else)
- ✨ Operador ternário
- ✨ Switch case
- ✨ Tomada de decisões complexas

**Pré-requisito:** Domine os operadores desta semana!

---

**Professor:** Marcelo Damasceno de Melo

**Curso:** Introdução ao JavaScript

**Semana:** 2 de 8

**Próxima aula:** Estruturas Condicionais

---
