# Roteiro de Estudos: Introdução ao JavaScript - Semana 4

## Objetivo da Semana

Dominar as estruturas de repetição (loops) do JavaScript, aprendendo a executar código múltiplas vezes de forma eficiente e automatizada, essencial para processar listas, realizar cálculos iterativos e criar algoritmos mais complexos.

---

## ⚠️ PRÉ-REQUISITOS OBRIGATÓRIOS

**ATENÇÃO:** Antes de iniciar esta semana, você DEVE dominar:

- ✅ Variáveis (`let` e `const`)
- ✅ Operadores aritméticos e de atribuição (++, --, +=, -=)
- ✅ Operadores de comparação (===, !==, <, >, <=, >=)
- ✅ Operadores lógicos (&&, ||, !)
- ✅ Estruturas condicionais (if, else if, else)

**Se ainda tem dúvidas:** Revise as Semanas 1, 2 e 3 antes de prosseguir!

---

## Parte 1: Conceito de Repetição (Loops)

### 1.1: O que são Loops?

Loops (laços de repetição) permitem executar um bloco de código **várias vezes** sem precisar reescrevê-lo.

**Analogia da vida real:**

- Escovar cada dente (repetir 32 vezes)
- Subir cada degrau de uma escada
- Ler cada página de um livro
- Processar cada item de uma lista de compras

**Por que usar loops?**

```javascript
// ❌ SEM LOOP - Código repetitivo
console.log("Contagem: 1");
console.log("Contagem: 2");
console.log("Contagem: 3");
console.log("Contagem: 4");
console.log("Contagem: 5");
// Imagine fazer isso 100 vezes...

// ✅ COM LOOP - Código eficiente
for (let i = 1; i <= 5; i++) {
  console.log("Contagem:", i);
}
```

### 1.2: Tipos de Loops em JavaScript

JavaScript possui 3 estruturas principais de repetição:

1. **for** - Quando você sabe quantas vezes vai repetir
2. **while** - Quando você repete enquanto uma condição for verdadeira
3. **do-while** - Executa pelo menos uma vez, depois verifica a condição

---

## Parte 2: Loop For

### 2.1: Estrutura do For

O loop `for` é o mais usado quando você sabe **exatamente quantas iterações** precisa fazer.

**Sintaxe:**

```javascript
for (inicialização; condição; atualização) {
  // código a ser repetido
}
```

**Componentes:**

1. **Inicialização**: Executada uma vez no início (cria variável de controle)
2. **Condição**: Verificada antes de cada iteração (enquanto for true, continua)
3. **Atualização**: Executada ao final de cada iteração (geralmente incrementa)
4. **Corpo**: Código que será repetido

### 2.2: Primeiro Exemplo - Contagem Simples

```javascript
// Contar de 1 a 5
for (let i = 1; i <= 5; i++) {
  console.log("Número:", i);
}

// Saída:
// Número: 1
// Número: 2
// Número: 3
// Número: 4
// Número: 5

// Entendendo o fluxo:
// 1ª iteração: i = 1, verifica (1 <= 5) true, executa, depois i++ (i vira 2)
// 2ª iteração: i = 2, verifica (2 <= 5) true, executa, depois i++ (i vira 3)
// 3ª iteração: i = 3, verifica (3 <= 5) true, executa, depois i++ (i vira 4)
// 4ª iteração: i = 4, verifica (4 <= 5) true, executa, depois i++ (i vira 5)
// 5ª iteração: i = 5, verifica (5 <= 5) true, executa, depois i++ (i vira 6)
// 6ª tentativa: i = 6, verifica (6 <= 5) false, PARA o loop
```

### 2.3: Variações do For

```javascript
// Contar de 0 a 4 (padrão em programação)
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Saída: 0, 1, 2, 3, 4

// Contar de trás para frente (decrescente)
for (let i = 5; i >= 1; i--) {
  console.log(i);
}
// Saída: 5, 4, 3, 2, 1

// Contar de 2 em 2
for (let i = 0; i <= 10; i += 2) {
  console.log(i);
}
// Saída: 0, 2, 4, 6, 8, 10

// Contar de 5 em 5
for (let i = 0; i <= 50; i += 5) {
  console.log(i);
}
// Saída: 0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50

// Números ímpares até 10
for (let i = 1; i <= 10; i += 2) {
  console.log(i);
}
// Saída: 1, 3, 5, 7, 9
```

### 2.4: Exemplos Práticos com For

```javascript
// Exemplo 1: Tabuada
const numero = 7;
console.log(`Tabuada do ${numero}:`);

for (let i = 1; i <= 10; i++) {
  const resultado = numero * i;
  console.log(`${numero} x ${i} = ${resultado}`);
}

// Exemplo 2: Soma acumulativa
let soma = 0;

for (let i = 1; i <= 100; i++) {
  soma += i; // soma = soma + i
}

console.log("Soma de 1 até 100:", soma); // 5050

// Exemplo 3: Contar apenas números pares
let contadorPares = 0;

for (let i = 1; i <= 20; i++) {
  if (i % 2 === 0) {
    console.log("Par encontrado:", i);
    contadorPares++;
  }
}

console.log("Total de pares:", contadorPares);

// Exemplo 4: Fatorial
const n = 5;
let fatorial = 1;

for (let i = 1; i <= n; i++) {
  fatorial *= i; // fatorial = fatorial * i
}

console.log(`Fatorial de ${n}:`, fatorial); // 120
// 5! = 5 × 4 × 3 × 2 × 1 = 120

// Exemplo 5: Contagem regressiva
console.log("Iniciando contagem regressiva:");

for (let i = 10; i >= 0; i--) {
  if (i === 0) {
    console.log("🚀 DECOLAGEM!");
  } else {
    console.log(i + "...");
  }
}
```

### 2.5: For com Strings

```javascript
// Percorrer cada caractere de uma string
const palavra = "JavaScript";

console.log("Letras da palavra:");
for (let i = 0; i < palavra.length; i++) {
  console.log(`Posição ${i}: ${palavra[i]}`);
}

// Saída:
// Posição 0: J
// Posição 1: a
// Posição 2: v
// Posição 3: a
// ...

// Contar vogais em uma palavra
const texto = "Programação";
let contadorVogais = 0;

for (let i = 0; i < texto.length; i++) {
  const letra = texto[i].toLowerCase();

  if (
    letra === "a" ||
    letra === "e" ||
    letra === "i" ||
    letra === "o" ||
    letra === "u"
  ) {
    contadorVogais++;
  }
}

console.log("Total de vogais:", contadorVogais);

// Inverter uma string
const original = "JavaScript";
let invertida = "";

for (let i = original.length - 1; i >= 0; i--) {
  invertida += original[i];
}

console.log("Original:", original); // JavaScript
console.log("Invertida:", invertida); // tpircSavaJ
```

### 2.6: Loops Aninhados (For dentro de For)

```javascript
// Exemplo 1: Tabuada completa (1 a 10)
console.log("=== TABUADA COMPLETA ===\n");

for (let i = 1; i <= 10; i++) {
  console.log(`Tabuada do ${i}:`);

  for (let j = 1; j <= 10; j++) {
    console.log(`${i} x ${j} = ${i * j}`);
  }

  console.log(""); // linha em branco
}

// Exemplo 2: Padrão de estrelas
console.log("Pirâmide de estrelas:");

for (let i = 1; i <= 5; i++) {
  let linha = "";

  for (let j = 1; j <= i; j++) {
    linha += "* ";
  }

  console.log(linha);
}

// Saída:
// *
// * *
// * * *
// * * * *
// * * * * *

// Exemplo 3: Matriz de números
console.log("Matriz 3x3:");

for (let linha = 1; linha <= 3; linha++) {
  let textoLinha = "";

  for (let coluna = 1; coluna <= 3; coluna++) {
    textoLinha += `[${linha},${coluna}] `;
  }

  console.log(textoLinha);
}

// Saída:
// [1,1] [1,2] [1,3]
// [2,1] [2,2] [2,3]
// [3,1] [3,2] [3,3]

// Exemplo 4: Combinações de produtos
const cores = ["vermelho", "azul", "verde"];
const tamanhos = ["P", "M", "G"];

console.log("Combinações disponíveis:");

for (let i = 0; i < cores.length; i++) {
  for (let j = 0; j < tamanhos.length; j++) {
    console.log(`Camiseta ${cores[i]} - Tamanho ${tamanhos[j]}`);
  }
}
```

---

## Parte 3: Loop While

### 3.1: Estrutura do While

O loop `while` repete enquanto uma condição for verdadeira. Use quando **não sabe quantas vezes** vai repetir.

**Sintaxe:**

```javascript
while (condição) {
  // código a ser repetido
  // IMPORTANTE: atualizar variável para evitar loop infinito!
}
```

**Fluxo:**

1. Verifica a condição
2. Se true: executa o bloco e volta ao passo 1
3. Se false: sai do loop

### 3.2: Exemplos Básicos

```javascript
// Exemplo 1: Contagem simples
let contador = 1;

while (contador <= 5) {
  console.log("Contagem:", contador);
  contador++; // CRUCIAL: incrementar para não ficar infinito
}

// Exemplo 2: Somar até atingir meta
let soma = 0;
let numero = 1;

while (soma < 100) {
  soma += numero;
  console.log(`Adicionando ${numero}, soma atual: ${soma}`);
  numero++;
}

console.log("Meta de 100 atingida!");
console.log("Soma final:", soma);

// Exemplo 3: Dobrar valor até limite
let valor = 1;

while (valor < 1000) {
  console.log("Valor atual:", valor);
  valor *= 2; // dobra o valor
}

console.log("Valor final:", valor);
// Saída: 1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024
```

### 3.3: While vs For

```javascript
// Mesma funcionalidade com FOR e WHILE

// COM FOR (sabemos o número de iterações)
for (let i = 1; i <= 5; i++) {
  console.log(i);
}

// COM WHILE (equivalente)
let i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}

// WHILE é melhor quando não sabemos quantas iterações
// Exemplo: Ler entrada do usuário até digitar "sair"
let continuar = true;
let tentativas = 0;

while (continuar) {
  tentativas++;
  console.log("Tentativa", tentativas);

  // Simulação: para após 3 tentativas
  if (tentativas === 3) {
    continuar = false;
  }
}
```

### 3.4: Exemplos Práticos com While

```javascript
// Exemplo 1: Validação de senha
const senhaCorreta = "12345";
let senhaDigitada = "";
let tentativas = 0;
const maxTentativas = 3;

while (senhaDigitada !== senhaCorreta && tentativas < maxTentativas) {
  tentativas++;
  console.log(`Tentativa ${tentativas} de ${maxTentativas}`);

  // Simulação de entrada do usuário
  senhaDigitada = tentativas === 2 ? "12345" : "senha_errada";

  if (senhaDigitada === senhaCorreta) {
    console.log("✓ Senha correta! Acesso liberado.");
  } else if (tentativas < maxTentativas) {
    console.log("✗ Senha incorreta. Tente novamente.");
  }
}

if (senhaDigitada !== senhaCorreta) {
  console.log("✗ Número máximo de tentativas atingido. Acesso bloqueado.");
}

// Exemplo 2: Contagem de dígitos
let numero = 12345;
let digitos = 0;

while (numero > 0) {
  numero = Math.floor(numero / 10); // remove último dígito
  digitos++;
}

console.log("Número de dígitos:", digitos); // 5

// Exemplo 3: Sequência de Fibonacci até limite
let a = 0;
let b = 1;
const limite = 100;

console.log("Sequência de Fibonacci até", limite + ":");
console.log(a);
console.log(b);

while (a + b <= limite) {
  const proximo = a + b;
  console.log(proximo);
  a = b;
  b = proximo;
}
// Saída: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89

// Exemplo 4: Sistema de saldo bancário
let saldo = 1000.0;
let saque = 0;
let totalSacado = 0;

console.log("Saldo inicial: R$", saldo.toFixed(2));

while (saldo > 0) {
  saque = 100; // saque fixo de R$ 100

  if (saldo >= saque) {
    saldo -= saque;
    totalSacado += saque;
    console.log(
      `Saque de R$ ${saque.toFixed(2)} - Saldo: R$ ${saldo.toFixed(2)}`
    );
  } else {
    console.log(`Último saque: R$ ${saldo.toFixed(2)}`);
    totalSacado += saldo;
    saldo = 0;
  }
}

console.log("\nTotal sacado: R$", totalSacado.toFixed(2));
```

### 3.5: ⚠️ CUIDADO: Loop Infinito!

```javascript
// ❌ LOOP INFINITO - NUNCA FAÇA ISSO!
/*
let x = 1;
while (x <= 10) {
    console.log(x);
    // ESQUECEU de incrementar x!
    // x sempre será 1, condição sempre true
    // Loop nunca termina!
}
*/

// ✅ CORRETO - Sempre atualize a variável de controle
let x = 1;
while (x <= 10) {
  console.log(x);
  x++; // IMPORTANTE!
}

// Sinais de loop infinito:
// - Navegador trava
// - Console para de responder
// - Mensagem "página não responde"
// Solução: Feche a aba ou reinicie o navegador
```

---

## Parte 4: Loop Do-While

### 4.1: Estrutura do Do-While

O loop `do-while` é similar ao `while`, mas **garante pelo menos uma execução** antes de verificar a condição.

**Sintaxe:**

```javascript
do {
  // código a ser repetido
  // executado PELO MENOS UMA VEZ
} while (condição);
```

**Diferença fundamental:**

- **while**: Verifica ANTES de executar (pode não executar nenhuma vez)
- **do-while**: Executa PRIMEIRO, depois verifica (sempre executa pelo menos uma vez)

### 4.2: While vs Do-While

```javascript
// Exemplo: Condição falsa desde o início

// COM WHILE - NÃO executa nenhuma vez
let i = 10;
while (i < 5) {
  console.log("While:", i); // Não imprime nada
  i++;
}

// COM DO-WHILE - Executa pelo menos uma vez
let j = 10;
do {
  console.log("Do-While:", j); // Imprime "Do-While: 10"
  j++;
} while (j < 5);

// Do-while garante execução mesmo com condição falsa inicial
```

### 4.3: Exemplos Práticos

```javascript
// Exemplo 1: Menu que sempre exibe pelo menos uma vez
let opcao;

do {
  console.log("\n=== MENU PRINCIPAL ===");
  console.log("1 - Consultar saldo");
  console.log("2 - Fazer depósito");
  console.log("3 - Fazer saque");
  console.log("4 - Sair");
  console.log("=====================");

  // Simulação de entrada do usuário
  opcao = 4; // usuário escolheu sair

  console.log("Opção escolhida:", opcao);
} while (opcao !== 4);

console.log("Saindo do sistema...");

// Exemplo 2: Validação de entrada
let numero;

do {
  // Simulação: usuário digitando números
  numero = Math.floor(Math.random() * 20);
  console.log("Número digitado:", numero);

  if (numero < 1 || numero > 10) {
    console.log("❌ Número inválido! Digite entre 1 e 10.");
  }
} while (numero < 1 || numero > 10);

console.log("✓ Número válido aceito:", numero);

// Exemplo 3: Jogo de adivinhação
const numeroSecreto = 7;
let tentativa;
let tentativasFeitas = 0;

do {
  tentativasFeitas++;
  // Simulação de palpite do usuário
  tentativa = Math.floor(Math.random() * 10) + 1;

  console.log(`Tentativa ${tentativasFeitas}: ${tentativa}`);

  if (tentativa < numeroSecreto) {
    console.log("📈 Muito baixo!");
  } else if (tentativa > numeroSecreto) {
    console.log("📉 Muito alto!");
  } else {
    console.log(`🎉 Parabéns! Acertou em ${tentativasFeitas} tentativas!`);
  }
} while (tentativa !== numeroSecreto && tentativasFeitas < 5);

if (tentativa !== numeroSecreto) {
  console.log(`😔 Suas tentativas acabaram. O número era ${numeroSecreto}`);
}

// Exemplo 4: Processo que deve executar pelo menos uma vez
let saldoMinimo = 100;
let saldoAtual = 50;
let deposito;

console.log("Saldo atual: R$", saldoAtual);
console.log("Saldo mínimo necessário: R$", saldoMinimo);

do {
  const necessario = saldoMinimo - saldoAtual;
  console.log(
    `\nVocê precisa depositar pelo menos R$ ${necessario.toFixed(2)}`
  );

  deposito = 30; // simulação de depósito
  saldoAtual += deposito;

  console.log(`Depositado: R$ ${deposito.toFixed(2)}`);
  console.log(`Novo saldo: R$ ${saldoAtual.toFixed(2)}`);
} while (saldoAtual < saldoMinimo);

console.log("\n✓ Saldo mínimo atingido!");
```

---

## Parte 5: Break e Continue

### 5.1: Instrução Break

`break` **interrompe completamente** o loop, saindo dele imediatamente.

```javascript
// Exemplo 1: Procurar um número específico
console.log("Procurando o número 7:");

for (let i = 1; i <= 10; i++) {
  console.log("Verificando:", i);

  if (i === 7) {
    console.log("✓ Número 7 encontrado!");
    break; // SAI DO LOOP imediatamente
  }
}

console.log("Fim da busca");
// Saída: 1, 2, 3, 4, 5, 6, 7, "encontrado", "fim"

// Exemplo 2: Parar quando atingir limite
let soma = 0;

for (let i = 1; i <= 100; i++) {
  soma += i;
  console.log(`i: ${i}, soma: ${soma}`);

  if (soma >= 50) {
    console.log("Soma atingiu 50, parando...");
    break;
  }
}

// Exemplo 3: Sistema de tentativas limitadas
const senhaCorreta = "abc123";
const maxTentativas = 3;

for (let tentativa = 1; tentativa <= maxTentativas; tentativa++) {
  console.log(`\nTentativa ${tentativa} de ${maxTentativas}`);

  // Simulação de entrada
  const senhaDigitada = tentativa === 2 ? "abc123" : "errado";

  if (senhaDigitada === senhaCorreta) {
    console.log("✓ Login realizado com sucesso!");
    break; // Não precisa continuar tentando
  } else {
    console.log("✗ Senha incorreta");
  }
}

// Exemplo 4: Busca em lista de nomes
const nomes = ["Ana", "Bruno", "Carlos", "Diana", "Eduardo"];
const nomeBuscado = "Carlos";
let encontrado = false;

for (let i = 0; i < nomes.length; i++) {
  console.log(`Verificando: ${nomes[i]}`);

  if (nomes[i] === nomeBuscado) {
    console.log(`✓ ${nomeBuscado} encontrado na posição ${i}!`);
    encontrado = true;
    break;
  }
}

if (!encontrado) {
  console.log(`✗ ${nomeBuscado} não foi encontrado`);
}
```

### 5.2: Instrução Continue

`continue` **pula para a próxima iteração**, ignorando o código restante do bloco atual.

```javascript
// Exemplo 1: Pular números pares
console.log("Números ímpares de 1 a 10:");

for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    continue; // Pula para próxima iteração
  }
  console.log(i);
}
// Saída: 1, 3, 5, 7, 9

// Exemplo 2: Processar apenas valores válidos
const numeros = [10, -5, 20, 0, 15, -3, 8];
let somaPositivos = 0;

for (let i = 0; i < numeros.length; i++) {
  if (numeros[i] <= 0) {
    console.log(`Ignorando ${numeros[i]} (não é positivo)`);
    continue; // Ignora números negativos ou zero
  }

  somaPositivos += numeros[i];
  console.log(`Adicionando ${numeros[i]}, soma: ${somaPositivos}`);
}

console.log("Soma dos positivos:", somaPositivos); // 53

// Exemplo 3: Pular elementos específicos
const produtos = [
  "Arroz",
  "Feijão",
  "INDISPONÍVEL",
  "Macarrão",
  "INDISPONÍVEL",
  "Açúcar",
];

console.log("Produtos disponíveis:");

for (let i = 0; i < produtos.length; i++) {
  if (produtos[i] === "INDISPONÍVEL") {
    continue; // Não exibe produtos indisponíveis
  }
  console.log(`- ${produtos[i]}`);
}

// Exemplo 4: Validação de dados
const idades = [25, -10, 30, 150, 18, 0, 45];

console.log("Idades válidas (entre 1 e 120):");

for (let i = 0; i < idades.length; i++) {
  if (idades[i] < 1 || idades[i] > 120) {
    console.log(`❌ ${idades[i]} - idade inválida (ignorada)`);
    continue;
  }

  console.log(`✓ ${idades[i]} - idade válida`);
}
```

### 5.3: Break vs Continue

```javascript
// Comparação direta

console.log("=== COM BREAK ===");
for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    console.log("Encontrou 5, PARANDO tudo");
    break; // Para o loop completamente
  }
  console.log(i);
}
// Saída: 1, 2, 3, 4, "Encontrou 5, PARANDO tudo"

console.log("\n=== COM CONTINUE ===");
for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    console.log("Pulando o 5");
    continue; // Pula só esta iteração
  }
  console.log(i);
}
// Saída: 1, 2, 3, 4, "Pulando o 5", 6, 7, 8, 9, 10
```

### 5.4: Break em Loops Aninhados

```javascript
// Break sai apenas do loop mais interno

console.log("Procurando produto:");

const categorias = ["Eletrônicos", "Roupas", "Alimentos"];
const produtos = ["TV", "Celular", "Notebook"];
let encontrou = false;

for (let i = 0; i < categorias.length; i++) {
  console.log(`\nVerificando categoria: ${categorias[i]}`);

  for (let j = 0; j < produtos.length; j++) {
    console.log(`  - ${produtos[j]}`);

    if (produtos[j] === "Celular") {
      console.log("  ✓ Celular encontrado!");
      encontrou = true;
      break; // Sai apenas do loop interno (produtos)
    }
  }

  if (encontrou) {
    break; // Agora sai do loop externo (categorias)
  }
}

// Para sair de loops aninhados de uma vez, use flag (variável boolean)
```

---

## 🎓 Parte 6: Exercícios Práticos

### Exercício 1: Tabuada Simples ⭐

**Objetivo:** Praticar loop for básico.

**Tarefa:**

```javascript
const numero = 6;

// Crie um loop que exiba a tabuada do número de 1 a 10
// Formato: "6 x 1 = 6"
```

---

### Exercício 2: Soma de Números ⭐

**Objetivo:** Acumular valores em loop.

**Tarefa:**

```javascript
// Calcule a soma de todos os números de 1 a 50
// Use um loop for
// Exiba o resultado final
```

---

### Exercício 3: Contagem Regressiva ⭐

**Objetivo:** Loop decrescente.

**Tarefa:**

```javascript
// Faça uma contagem regressiva de 20 até 0
// Quando chegar a 0, exiba "ACABOU!"
// Use for
```

---

### Exercício 4: Números Pares ⭐⭐

**Objetivo:** Usar condicionais dentro de loops.

**Tarefa:**

```javascript
// Exiba apenas os números PARES de 1 a 30
// Use for e if
// Conte quantos números pares foram exibidos
```

---

### Exercício 5: Fatorial ⭐⭐

**Objetivo:** Cálculo iterativo.

**Tarefa:**

```javascript
const n = 6;

// Calcule o fatorial de n (n!)
// 6! = 6 × 5 × 4 × 3 × 2 × 1 = 720
// Use for ou while
```

---

### Exercício 6: Validação com While ⭐⭐

**Objetivo:** Loop com condição de parada.

**Tarefa:**

```javascript
let senha = "";
const senhaCorreta = "javascript";
let tentativas = 0;
const maxTentativas = 3;

// Simule tentativas de login
// Continue pedindo até acertar OU atingir máximo de tentativas
// Use while
// Exiba mensagem apropriada ao final
```

---

### Exercício 7: Sequência de Fibonacci ⭐⭐⭐

**Objetivo:** Sequência matemática com loop.

**Tarefa:**

```javascript
const limite = 15;

// Exiba os primeiros 15 números da sequência de Fibonacci
// 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89...
// Cada número é a soma dos dois anteriores
```

---

### Exercício 8: Pirâmide de Asteriscos ⭐⭐⭐

**Objetivo:** Loops aninhados.

**Tarefa:**

```javascript
const altura = 5;

// Desenhe uma pirâmide de asteriscos
// Saída esperada:
// *
// **
// ***
// ****
// *****

// Use loops aninhados (for dentro de for)
```

---

### Exercício 9: Busca com Break ⭐⭐⭐

**Objetivo:** Usar break eficientemente.

**Tarefa:**

```javascript
const numeros = [3, 7, 12, 5, 18, 9, 21, 15];
const numeroBuscado = 18;

// Procure o número no array
// Quando encontrar, exiba a posição e PARE a busca
// Se não encontrar, exiba mensagem
// Use for e break
```

---

### Exercício 10: Filtro com Continue ⭐⭐⭐

**Objetivo:** Pular elementos com continue.

**Tarefa:**

```javascript
const notas = [8.5, 4.0, 7.5, 3.5, 9.0, 5.5, 6.0, 2.0];

// Exiba apenas as notas >= 7.0 (aprovados)
// Use continue para pular as reprovações
// Conte quantos foram aprovados
```

---

## Parte 7: Desafios Avançados (Opcional)

### Desafio 1: Números Primos 🔥🔥

```javascript
const limite = 50;

// Encontre e exiba todos os números primos até 50
// Número primo: divisível apenas por 1 e ele mesmo
// Exemplos: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29...

// Dica: Para cada número, teste se é divisível por algum número menor
```

---

### Desafio 2: Padrão de Números 🔥🔥

```javascript
// Crie o seguinte padrão usando loops:
// 1
// 1 2
// 1 2 3
// 1 2 3 4
// 1 2 3 4 5

// Use loops aninhados
```

---

### Desafio 3: Jogo de Adivinhação Completo 🔥🔥🔥

```javascript
// Crie um jogo completo onde:
// 1. Gera número aleatório entre 1 e 100
// 2. Usuário tem 7 tentativas para adivinhar
// 3. A cada tentativa, diz se é "muito alto" ou "muito baixo"
// 4. Se acertar, mostra em quantas tentativas
// 5. Se errar todas, mostra o número secreto

const numeroSecreto = Math.floor(Math.random() * 100) + 1;

// Seu código aqui
// Use do-while ou while
// Use break quando acertar
```

---

### Desafio 4: Calculadora de Média de Turma 🔥🔥🔥

```javascript
// Simule uma turma com 10 alunos
// Para cada aluno, tem 3 notas
// Calcule:
// - Média de cada aluno
// - Quantos aprovados (média >= 7)
// - Quantos em recuperação (5 <= média < 7)
// - Quantos reprovados (média < 5)
// - Média geral da turma

// Use loops aninhados
// Gere notas aleatórias entre 0 e 10
```

**Estrutura sugerida:**

```javascript
const totalAlunos = 10;
const notasPorAluno = 3;
let somaGeralTurma = 0;
let aprovados = 0;
let recuperacao = 0;
let reprovados = 0;

console.log("=== BOLETIM DA TURMA ===\n");

for (let aluno = 1; aluno <= totalAlunos; aluno++) {
  console.log(`Aluno ${aluno}:`);
  let somaAluno = 0;

  // Gerar e exibir notas do aluno
  for (let prova = 1; prova <= notasPorAluno; prova++) {
    const nota = (Math.random() * 10).toFixed(1);
    // Continue o código...
  }

  // Calcular média do aluno
  // Classificar (aprovado/recuperação/reprovado)
  // Acumular para média geral
}

// Exibir estatísticas finais
```

---

## Parte 8: Projeto da Semana

### 🎯 Sistema de Análise de Vendas

**Objetivo:** Criar um sistema completo que analisa vendas de uma loja durante um mês.

**Requisitos:**

```javascript
// ===== CONFIGURAÇÕES =====
const diasDoMes = 30;
const metaDiaria = 1000.0;
const metaMensal = 25000.0;

// ===== VARIÁVEIS DE CONTROLE =====
let totalVendas = 0;
let melhorDia = 0;
let piorDia = 0;
let maiorVenda = 0;
let menorVenda = Infinity;
let diasAcimaDaMeta = 0;
let diasAbaixoDaMeta = 0;

console.log("========================================");
console.log("   RELATÓRIO DE VENDAS DO MÊS   ");
console.log("========================================\n");

// ===== PARTE 1: SIMULAÇÃO DAS VENDAS DIÁRIAS =====
console.log("--- VENDAS DIÁRIAS ---\n");

for (let dia = 1; dia <= diasDoMes; dia++) {
  // Gerar venda aleatória entre R$ 500 e R$ 2000
  const vendaDia = (Math.random() * 1500 + 500).toFixed(2);
  const vendaNum = parseFloat(vendaDia);

  // Acumular total
  totalVendas += vendaNum;

  // Verificar se bateu meta
  const bateuMeta = vendaNum >= metaDiaria;

  if (bateuMeta) {
    diasAcimaDaMeta++;
  } else {
    diasAbaixoDaMeta++;
  }

  // Exibir dia
  console.log(`Dia ${dia}: R$ ${vendaDia} ${bateuMeta ? "✓" : "✗"}`);

  // Identificar melhor e pior dia
  if (vendaNum > maiorVenda) {
    maiorVenda = vendaNum;
    melhorDia = dia;
  }

  if (vendaNum < menorVenda) {
    menorVenda = vendaNum;
    piorDia = dia;
  }
}

// ===== PARTE 2: ANÁLISE DE DESEMPENHO POR SEMANA =====
console.log("\n--- ANÁLISE POR SEMANA ---\n");

// Implemente análise semanal aqui
// Divida os 30 dias em semanas e calcule total de cada

// ===== PARTE 3: ESTATÍSTICAS FINAIS =====
console.log("\n========================================");
console.log("          ESTATÍSTICAS FINAIS           ");
console.log("========================================\n");

const mediaDiaria = totalVendas / diasDoMes;
const porcentagemMeta = (totalVendas / metaMensal) * 100;
const bateuMetaMensal = totalVendas >= metaMensal;

console.log(`Total de vendas: R$ ${totalVendas.toFixed(2)}`);
console.log(`Média diária: R$ ${mediaDiaria.toFixed(2)}`);
console.log(`Meta mensal: R$ ${metaMensal.toFixed(2)}`);
console.log(`Atingido: ${porcentagemMeta.toFixed(1)}%`);
console.log(
  `Status: ${bateuMetaMensal ? "✓ META BATIDA!" : "✗ Meta não atingida"}\n`
);

console.log(`Melhor dia: Dia ${melhorDia} (R$ ${maiorVenda.toFixed(2)})`);
console.log(`Pior dia: Dia ${piorDia} (R$ ${menorVenda.toFixed(2)})`);
console.log(`Dias acima da meta: ${diasAcimaDaMeta}`);
console.log(`Dias abaixo da meta: ${diasAbaixoDaMeta}\n`);

// ===== PARTE 4: PROJEÇÃO =====
console.log("--- PROJEÇÃO ---\n");

// Se mantiver a média atual, quanto vai vender no próximo mês?
const projecaoProximoMes = mediaDiaria * 30;
console.log(`Projeção próximo mês: R$ ${projecaoProximoMes.toFixed(2)}`);

// Quantos dias precisaria vender na meta para atingir objetivo mensal?
const diasNecessarios = Math.ceil(metaMensal / metaDiaria);
console.log(`Dias na meta necessários: ${diasNecessarios} dias`);

// ===== PARTE 5: BÔNUS - SIMULAÇÃO DE CRESCIMENTO =====
console.log("\n--- SIMULAÇÃO DE CRESCIMENTO ---\n");

// Se crescer 5% ao mês, qual será a venda em 12 meses?
let vendaAtual = totalVendas;
const taxaCrescimento = 1.05; // 5%

console.log("Projeção de crescimento (5% ao mês):");
for (let mes = 1; mes <= 12; mes++) {
  vendaAtual *= taxaCrescimento;
  console.log(`Mês ${mes}: R$ ${vendaAtual.toFixed(2)}`);
}

console.log("\n========================================");
```

**Critérios de avaliação:**

- [ ] Usa for para iterar os dias
- [ ] Calcula estatísticas corretamente
- [ ] Identifica melhor e pior dia
- [ ] Conta dias acima/abaixo da meta
- [ ] Implementa análise semanal
- [ ] Faz projeções usando loops
- [ ] Código bem organizado e comentado
- [ ] Saída formatada e legível
- [ ] Usa break ou continue apropriadamente (se necessário)

**Desafios extras:**

- Adicione tendência de crescimento (vendas aumentam ao longo do mês)
- Simule dias de semana vs fins de semana (fins vendem menos)
- Crie gráfico de barras em texto (usando asteriscos)
- Identifique sequência de dias consecutivos acima da meta

---

## Parte 9: Checklist de Aprendizado

Ao final da Semana 4, você deve ser capaz de:

- [ ] Entender quando e por que usar loops
- [ ] Implementar loop for com contador
- [ ] Usar for com diferentes incrementos
- [ ] Criar loops for decrescentes
- [ ] Implementar loops aninhados (for dentro de for)
- [ ] Usar while para repetição condicional
- [ ] Implementar do-while corretamente
- [ ] Diferenciar while de do-while
- [ ] Usar break para interromper loops
- [ ] Usar continue para pular iterações
- [ ] Evitar loops infinitos
- [ ] Combinar loops com condicionais
- [ ] Acumular valores em loops
- [ ] Processar strings com loops
- [ ] Resolver problemas iterativos

---

## Parte 10: Troubleshooting

### Problema 1: Loop infinito

```javascript
// ❌ ERRADO
let i = 0;
while (i < 10) {
  console.log(i);
  // Esqueceu i++
}

// ✅ CORRETO
let i = 0;
while (i < 10) {
  console.log(i);
  i++; // SEMPRE atualize a variável!
}
```

### Problema 2: Off-by-one error

```javascript
// ❌ ERRADO - Executa 11 vezes (0 a 10)
for (let i = 0; i <= 10; i++) {
  console.log(i);
}

// ✅ CORRETO - Executa 10 vezes (0 a 9)
for (let i = 0; i < 10; i++) {
  console.log(i);
}

// ✅ ALTERNATIVA - Executa 10 vezes (1 a 10)
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

### Problema 3: Variável de loop não definida

```javascript
// ❌ ERRADO - 'i' não existe fora do loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}
console.log(i); // ReferenceError!

// ✅ CORRETO - Declare fora se precisar usar depois
let i;
for (i = 0; i < 5; i++) {
  console.log(i);
}
console.log("Último valor:", i); // 5
```

### Problema 4: Break não funciona como esperado

```javascript
// ❌ Break só sai do loop mais interno
for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (j === 1) break; // Sai só do loop de j
    console.log(i, j);
  }
}

// ✅ Use flag para sair de ambos
let encontrou = false;
for (let i = 0; i < 3 && !encontrou; i++) {
  for (let j = 0; j < 3; j++) {
    if (j === 1) {
      encontrou = true;
      break;
    }
    console.log(i, j);
  }
}
```

---

## Parte 11: Boas Práticas

### ✅ FAÇA:

1. **Use nomes descritivos**

```javascript
// ❌ Ruim
for (let x = 0; x < y; x++) {}

// ✅ Bom
for (let i = 0; i < totalAlunos; i++) {}
for (let aluno = 0; aluno < turma.length; aluno++) {}
```

2. **Sempre atualize a variável de controle**

```javascript
while (contador < 10) {
  // código
  contador++; // CRUCIAL!
}
```

3. **Use for quando souber o número de iterações**

```javascript
// ✅ Bom uso do for
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

4. **Use while para condições dinâmicas**

```javascript
// ✅ Bom uso do while
while (saldo > 0 && !saldoInsuficiente) {
  // lógica complexa
}
```

5. **Comente loops complexos**

```javascript
// Processa cada aluno e calcula média
for (let i = 0; i < alunos.length; i++) {
  // código
}
```

### ❌ EVITE:

1. **Loops infinitos**

```javascript
// ❌ NUNCA faça isso
while (true) {
  // sem break ou condição de saída
}
```

2. **Modificar variável de controle dentro do loop**

```javascript
// ❌ Confuso
for (let i = 0; i < 10; i++) {
  i += 2; // Evite!
}
```

3. **Loops aninhados muito profundos**

```javascript
// ❌ Difícil de ler (3+ níveis)
for (...) {
    for (...) {
        for (...) {
            for (...) {
                // código
            }
        }
    }
}
```

---

## Recursos Adicionais

### Documentação:

- **MDN - Loops**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Loops_and_iteration
- **JavaScript.info - Loops**: https://javascript.info/while-for

### Visualizadores:

- **Python Tutor (funciona com JS)**: pythontutor.com/javascript.html
- **Visualize Code**: visualgo.net

---

## Preparação para Semana 5

Na próxima semana você aprenderá:

- ✨ Arrays (listas de dados)
- ✨ Manipulação de arrays
- ✨ Métodos de array (push, pop, etc.)
- ✨ Iteração em arrays

**Pré-requisito:** Domine loops, pois usaremos muito com arrays!

---

**Professor:** Marcelo Damasceno de Melo

**Curso:** Introdução ao JavaScript

**Semana:** 4 de 8

**Próxima aula:** Arrays

---

**Bons estudos! 🚀**
