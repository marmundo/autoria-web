# Roteiro de Estudos: Introdução ao JavaScript - Semana 3

## Objetivo da Semana

Dominar as estruturas condicionais do JavaScript, aprendendo a criar programas que tomam decisões com base em diferentes condições, tornando o código dinâmico e responsivo às situações do usuário.

---

## ⚠️ PRÉ-REQUISITOS OBRIGATÓRIOS

**ATENÇÃO:** Antes de iniciar esta semana, você DEVE dominar:

- ✅ Variáveis (`let` e `const`)
- ✅ Tipos de dados (string, number, boolean)
- ✅ Operadores de comparação (===, !==, <, >, <=, >=)
- ✅ Operadores lógicos (&&, ||, !)
- ✅ Expressões booleanas

**Se ainda tem dúvidas:** Revise as Semanas 1 e 2 antes de prosseguir!

---

## Parte 1: Estrutura Condicional If

### 1.1: Conceito Fundamental

A estrutura `if` permite executar um bloco de código **apenas se** uma condição for verdadeira.

**Analogia:** "SE está chovendo, ENTÃO leve guarda-chuva"

**Sintaxe básica:**

```javascript
if (condição) {
  // código executado se condição for true
}
```

### 1.2: Primeiro Exemplo - If Simples

```javascript
// Exemplo 1: Verificar maioridade
const idade = 20;

if (idade >= 18) {
  console.log("Você é maior de idade");
}
// Se idade < 18, nada acontece

// Exemplo 2: Verificar aprovação
const nota = 8.5;

if (nota >= 7) {
  console.log("Parabéns! Você foi aprovado!");
}

// Exemplo 3: Verificar usuário logado
const usuarioLogado = true;

if (usuarioLogado) {
  console.log("Bem-vindo ao sistema!");
}

// Exemplo 4: Verificar número par
const numero = 10;

if (numero % 2 === 0) {
  console.log("O número é par");
}
```

### 1.3: Blocos de Código

O código entre `{ }` é chamado de **bloco**. Pode ter múltiplas linhas.

```javascript
const temperatura = 35;

if (temperatura > 30) {
  console.log("Está muito quente!");
  console.log("Beba bastante água!");
  console.log("Use protetor solar!");
}

// Múltiplas condições
const saldo = 1500.0;
const valorCompra = 1200.0;

if (saldo >= valorCompra) {
  console.log("Compra aprovada!");
  const novoSaldo = saldo - valorCompra;
  console.log("Novo saldo: R$", novoSaldo);
}
```

### 1.4: If com Expressões Complexas

```javascript
// Usando operadores lógicos dentro do if
const idade = 25;
const temCarteiraMotorista = true;

if (idade >= 18 && temCarteiraMotorista) {
  console.log("Você pode alugar um carro");
}

// Múltiplas condições com OR
const diaSemana = "sábado";
const ehFeriado = false;

if (diaSemana === "sábado" || diaSemana === "domingo" || ehFeriado) {
  console.log("Aproveite seu dia de folga!");
}

// Negação
const temIngresso = false;

if (!temIngresso) {
  console.log("Você precisa comprar um ingresso");
}

// Exemplo prático: Sistema de descontos
const valorCompra = 150.0;
const ehClienteVIP = true;
const primeiraCompra = false;

if ((valorCompra > 100 && ehClienteVIP) || primeiraCompra) {
  console.log("Você ganhou 10% de desconto!");
  const desconto = valorCompra * 0.1;
  console.log("Desconto: R$", desconto.toFixed(2));
}
```

---

## Parte 2: Estrutura If-Else

### 2.1: Conceito

`if-else` permite executar um bloco de código quando a condição é verdadeira e **outro bloco** quando é falsa.

**Analogia:** "SE está chovendo, ENTÃO leve guarda-chuva, SENÃO leve óculos de sol"

**Sintaxe:**

```javascript
if (condição) {
  // executado se condição for true
} else {
  // executado se condição for false
}
```

### 2.2: Exemplos Práticos

```javascript
// Exemplo 1: Par ou ímpar
const numero = 7;

if (numero % 2 === 0) {
  console.log("O número é par");
} else {
  console.log("O número é ímpar");
}

// Exemplo 2: Maior ou menor de idade
const idade = 16;

if (idade >= 18) {
  console.log("Você é maior de idade");
  console.log("Pode tirar CNH");
} else {
  console.log("Você é menor de idade");
  console.log("Ainda não pode tirar CNH");
}

// Exemplo 3: Saldo suficiente
const saldo = 500.0;
const valorSaque = 600.0;

if (saldo >= valorSaque) {
  console.log("Saque realizado com sucesso!");
  const novoSaldo = saldo - valorSaque;
  console.log("Novo saldo: R$", novoSaldo.toFixed(2));
} else {
  console.log("Saldo insuficiente!");
  console.log("Saldo disponível: R$", saldo.toFixed(2));
  console.log("Valor solicitado: R$", valorSaque.toFixed(2));
}

// Exemplo 4: Aprovação ou reprovação
const nota = 5.5;
const notaMinima = 7.0;

if (nota >= notaMinima) {
  console.log("APROVADO!");
  console.log("Parabéns pelo seu desempenho!");
} else {
  console.log("REPROVADO");
  const pontosNecessarios = notaMinima - nota;
  console.log("Faltaram", pontosNecessarios, "pontos");
}
```

### 2.3: If-Else com Expressões Complexas

```javascript
// Sistema de acesso
const usuario = "admin";
const senha = "1234";

const usuarioCorreto = "admin";
const senhaCorreta = "1234";

if (usuario === usuarioCorreto && senha === senhaCorreta) {
  console.log("✓ Login realizado com sucesso!");
  console.log("Bem-vindo ao sistema, " + usuario);
} else {
  console.log("✗ Usuário ou senha incorretos!");
  console.log("Tente novamente");
}

// Sistema de estacionamento
const horasEstacionado = 3;
const ehCliente = true;

if (horasEstacionado <= 2 && ehCliente) {
  console.log("Estacionamento GRATUITO para clientes!");
} else {
  const valorHora = 5.0;
  const valorTotal = horasEstacionado * valorHora;
  console.log("Valor a pagar: R$", valorTotal.toFixed(2));
}
```

---

## Parte 3: Estrutura Else If

### 3.1: Conceito

`else if` permite testar **múltiplas condições** em sequência.

**Analogia:** "SE está chovendo → guarda-chuva, SENÃO SE está sol → óculos, SENÃO SE está frio → casaco"

**Sintaxe:**

```javascript
if (condição1) {
  // executado se condição1 for true
} else if (condição2) {
  // executado se condição1 for false E condição2 for true
} else if (condição3) {
  // executado se condição1 e condição2 forem false E condição3 for true
} else {
  // executado se TODAS as condições anteriores forem false
}
```

### 3.2: Exemplos Básicos

```javascript
// Exemplo 1: Classificação de nota
const nota = 8.5;

if (nota >= 9) {
  console.log("Conceito: A - Excelente!");
} else if (nota >= 7) {
  console.log("Conceito: B - Bom!");
} else if (nota >= 5) {
  console.log("Conceito: C - Regular");
} else {
  console.log("Conceito: D - Insuficiente");
}

// Exemplo 2: Faixa etária
const idade = 35;

if (idade < 12) {
  console.log("Classificação: Criança");
} else if (idade < 18) {
  console.log("Classificação: Adolescente");
} else if (idade < 60) {
  console.log("Classificação: Adulto");
} else {
  console.log("Classificação: Idoso");
}

// Exemplo 3: Sistema de descontos progressivos
const valorCompra = 350.0;
let desconto = 0;
let taxaDesconto = 0;

if (valorCompra >= 500) {
  taxaDesconto = 20;
  desconto = valorCompra * 0.2;
} else if (valorCompra >= 300) {
  taxaDesconto = 15;
  desconto = valorCompra * 0.15;
} else if (valorCompra >= 100) {
  taxaDesconto = 10;
  desconto = valorCompra * 0.1;
} else {
  taxaDesconto = 0;
  desconto = 0;
}

console.log("Valor da compra: R$", valorCompra.toFixed(2));
console.log("Desconto aplicado:", taxaDesconto + "%");
console.log("Valor do desconto: R$", desconto.toFixed(2));
console.log("Valor final: R$", (valorCompra - desconto).toFixed(2));
```

### 3.3: Exemplos Avançados

```javascript
// Sistema de classificação de IMC
const peso = 75;
const altura = 1.75;
const imc = peso / altura ** 2;

console.log("Seu IMC:", imc.toFixed(2));

if (imc < 18.5) {
  console.log("Classificação: Abaixo do peso");
  console.log("Recomendação: Consulte um nutricionista");
} else if (imc < 25) {
  console.log("Classificação: Peso normal");
  console.log("Recomendação: Mantenha hábitos saudáveis");
} else if (imc < 30) {
  console.log("Classificação: Sobrepeso");
  console.log("Recomendação: Considere atividade física");
} else if (imc < 35) {
  console.log("Classificação: Obesidade Grau I");
  console.log("Recomendação: Procure orientação médica");
} else if (imc < 40) {
  console.log("Classificação: Obesidade Grau II");
  console.log("Recomendação: Acompanhamento médico necessário");
} else {
  console.log("Classificação: Obesidade Grau III");
  console.log("Recomendação: Procure um médico urgentemente");
}

// Sistema de temperatura
const temperatura = 28;

if (temperatura < 0) {
  console.log("Está congelante! ❄️");
  console.log("Cuidado com gelo nas ruas");
} else if (temperatura < 15) {
  console.log("Está frio! 🧥");
  console.log("Vista um casaco");
} else if (temperatura < 25) {
  console.log("Temperatura agradável! 😊");
  console.log("Clima perfeito para passear");
} else if (temperatura < 35) {
  console.log("Está quente! ☀️");
  console.log("Use roupas leves");
} else {
  console.log("Está muito quente! 🔥");
  console.log("Evite exposição ao sol");
}
```

### 3.4: Condicionais Aninhadas (If dentro de If)

```javascript
// Sistema de aprovação com recuperação
const nota = 6.0;
const frequencia = 80; // porcentagem

if (frequencia >= 75) {
  console.log("✓ Frequência suficiente");

  if (nota >= 7) {
    console.log("✓ APROVADO POR MÉDIA");
  } else if (nota >= 5) {
    console.log("→ RECUPERAÇÃO");
    console.log("Você precisa fazer prova de recuperação");
  } else {
    console.log("✗ REPROVADO POR NOTA");
  }
} else {
  console.log("✗ REPROVADO POR FALTA");
  console.log("Frequência insuficiente:", frequencia + "%");
}

// Sistema de empréstimo bancário
const idade = 30;
const rendaMensal = 5000.0;
const temRestricao = false;
const valorEmprestimo = 20000.0;

if (idade >= 18 && idade <= 70) {
  console.log("✓ Idade válida");

  if (rendaMensal >= 2000) {
    console.log("✓ Renda suficiente");

    if (!temRestricao) {
      console.log("✓ Sem restrições no CPF");

      const parcelaMaxima = rendaMensal * 0.3;
      const valorParcela = valorEmprestimo / 24; // 24 meses

      if (valorParcela <= parcelaMaxima) {
        console.log("\n🎉 EMPRÉSTIMO APROVADO!");
        console.log("Valor: R$", valorEmprestimo.toFixed(2));
        console.log("Parcelas: 24x de R$", valorParcela.toFixed(2));
      } else {
        console.log("\n✗ Empréstimo negado");
        console.log("Parcela muito alta para sua renda");
      }
    } else {
      console.log("✗ CPF com restrição");
    }
  } else {
    console.log("✗ Renda insuficiente");
    console.log("Renda mínima: R$ 2000.00");
  }
} else {
  console.log("✗ Idade fora da faixa permitida");
}
```

---

## Parte 4: Operador Ternário

### 4.1: Conceito

O operador ternário é uma forma **compacta** de escrever if-else simples em **uma única linha**.

**Sintaxe:**

```javascript
condição ? valorSeVerdadeiro : valorSeFalso;
```

**Equivalente:**

```javascript
if (condição) {
  return valorSeVerdadeiro;
} else {
  return valorSeFalso;
}
```

### 4.2: Exemplos Básicos

```javascript
// Exemplo 1: Par ou ímpar
const numero = 8;
const tipo = numero % 2 === 0 ? "par" : "ímpar";
console.log("O número é", tipo);

// Comparação com if-else tradicional:
let tipo2;
if (numero % 2 === 0) {
  tipo2 = "par";
} else {
  tipo2 = "ímpar";
}

// Exemplo 2: Maior ou menor de idade
const idade = 17;
const status = idade >= 18 ? "maior de idade" : "menor de idade";
console.log("Você é", status);

// Exemplo 3: Aprovado ou reprovado
const nota = 7.5;
const resultado = nota >= 7 ? "APROVADO" : "REPROVADO";
console.log(resultado);

// Exemplo 4: Preço com desconto
const ehCliente = true;
const precoBase = 100.0;
const precoFinal = ehCliente ? precoBase * 0.9 : precoBase;
console.log("Preço: R$", precoFinal.toFixed(2));
```

### 4.3: Ternário em Expressões

```javascript
// Dentro de console.log
const saldo = 500;
console.log("Saldo:", saldo >= 0 ? "Positivo" : "Negativo");

// Dentro de template literals
const nome = "João";
const idade = 25;
console.log(`${nome} ${idade >= 18 ? "pode" : "não pode"} votar`);

// Atribuindo resultado direto
const pontos = 850;
const nivel = pontos >= 1000 ? "Ouro" : pontos >= 500 ? "Prata" : "Bronze";
console.log("Nível:", nivel);

// Calculando valores
const horasTrabalhadas = 45;
const valorHora = 50.0;
const salario =
  horasTrabalhadas * (horasTrabalhadas > 40 ? valorHora * 1.5 : valorHora);
console.log("Salário: R$", salario.toFixed(2));
```

### 4.4: Ternário Aninhado (Use com moderação!)

```javascript
// Classificação de nota com ternário aninhado
const nota = 8.5;
const conceito = nota >= 9 ? "A" : nota >= 7 ? "B" : nota >= 5 ? "C" : "D";
console.log("Conceito:", conceito);

// ⚠️ ATENÇÃO: Ternário aninhado pode ficar difícil de ler
// Para 3+ condições, prefira if-else-if

// Exemplo mais complexo (evite fazer assim!)
const idade = 25;
const temCarteira = true;
const resultado =
  idade >= 18
    ? temCarteira
      ? "Pode dirigir"
      : "Precisa de carteira"
    : "Muito jovem";
console.log(resultado);

// ✅ Melhor escrever assim:
if (idade < 18) {
  console.log("Muito jovem");
} else if (temCarteira) {
  console.log("Pode dirigir");
} else {
  console.log("Precisa de carteira");
}
```

### 4.5: Quando Usar Ternário vs If-Else

```javascript
// ✅ BOM USO: Atribuição simples
const status = isActive ? "Ativo" : "Inativo";

// ✅ BOM USO: Valor em expressão
console.log(`Status: ${isOnline ? "Online" : "Offline"}`);

// ❌ MAU USO: Múltiplas linhas de código
const resultado = condicao
  ? (console.log("texto1"), console.log("texto2"), valor1)
  : (console.log("texto3"), valor2);

// ✅ PREFIRA: If-else tradicional para lógica complexa
if (condicao) {
  console.log("texto1");
  console.log("texto2");
  resultado = valor1;
} else {
  console.log("texto3");
  resultado = valor2;
}
```

---

## Parte 5: Switch Case

### 5.1: Conceito

`switch` é usado quando você precisa comparar **uma variável com vários valores possíveis**.

**Quando usar:**

- Múltiplas comparações de igualdade (===)
- Valores discretos/específicos (não intervalos)
- Código mais limpo que muitos else-if

**Sintaxe:**

```javascript
switch (expressão) {
  case valor1:
    // código se expressão === valor1
    break;
  case valor2:
    // código se expressão === valor2
    break;
  default:
  // código se nenhum case corresponder
}
```

### 5.2: Exemplos Básicos

```javascript
// Exemplo 1: Dias da semana
const diaSemana = 3;

switch (diaSemana) {
  case 1:
    console.log("Domingo");
    break;
  case 2:
    console.log("Segunda-feira");
    break;
  case 3:
    console.log("Terça-feira");
    break;
  case 4:
    console.log("Quarta-feira");
    break;
  case 5:
    console.log("Quinta-feira");
    break;
  case 6:
    console.log("Sexta-feira");
    break;
  case 7:
    console.log("Sábado");
    break;
  default:
    console.log("Dia inválido");
}

// Exemplo 2: Meses do ano
const mes = 12;

switch (mes) {
  case 1:
    console.log("Janeiro");
    break;
  case 2:
    console.log("Fevereiro");
    break;
  case 3:
    console.log("Março");
    break;
  // ... outros meses
  case 12:
    console.log("Dezembro");
    break;
  default:
    console.log("Mês inválido");
}

// Exemplo 3: Operações matemáticas
const operacao = "+";
const num1 = 10;
const num2 = 5;
let resultado;

switch (operacao) {
  case "+":
    resultado = num1 + num2;
    console.log("Resultado:", resultado);
    break;
  case "-":
    resultado = num1 - num2;
    console.log("Resultado:", resultado);
    break;
  case "*":
    resultado = num1 * num2;
    console.log("Resultado:", resultado);
    break;
  case "/":
    resultado = num1 / num2;
    console.log("Resultado:", resultado);
    break;
  default:
    console.log("Operação inválida");
}
```

### 5.3: Importância do Break

O `break` é **crucial** no switch. Sem ele, o código continua executando os próximos cases!

```javascript
// ⚠️ SEM BREAK (fall-through)
const opcao = 1;

switch (opcao) {
  case 1:
    console.log("Opção 1 executada");
  // sem break!
  case 2:
    console.log("Opção 2 executada");
  // sem break!
  case 3:
    console.log("Opção 3 executada");
    break;
}
// Saída:
// Opção 1 executada
// Opção 2 executada
// Opção 3 executada

// ✅ COM BREAK (comportamento esperado)
switch (opcao) {
  case 1:
    console.log("Opção 1 executada");
    break;
  case 2:
    console.log("Opção 2 executada");
    break;
  case 3:
    console.log("Opção 3 executada");
    break;
}
// Saída:
// Opção 1 executada
```

### 5.4: Fall-Through Intencional

Às vezes, queremos que múltiplos cases executem o mesmo código:

```javascript
// Exemplo 1: Dias úteis vs fim de semana
const dia = "sábado";

switch (dia) {
  case "segunda":
  case "terça":
  case "quarta":
  case "quinta":
  case "sexta":
    console.log("Dia útil - Precisa trabalhar");
    break;
  case "sábado":
  case "domingo":
    console.log("Fim de semana - Descanse!");
    break;
  default:
    console.log("Dia inválido");
}

// Exemplo 2: Estações do ano
const mes = 6;

switch (mes) {
  case 12:
  case 1:
  case 2:
    console.log("Verão");
    break;
  case 3:
  case 4:
  case 5:
    console.log("Outono");
    break;
  case 6:
  case 7:
  case 8:
    console.log("Inverno");
    break;
  case 9:
  case 10:
  case 11:
    console.log("Primavera");
    break;
  default:
    console.log("Mês inválido");
}

// Exemplo 3: Classificação de vogais e consoantes
const letra = "a";

switch (letra) {
  case "a":
  case "e":
  case "i":
  case "o":
  case "u":
    console.log("Vogal");
    break;
  default:
    console.log("Consoante");
}
```

### 5.5: Switch vs If-Else

```javascript
// ✅ BOM USO DO SWITCH: Valores específicos
const cor = "vermelho";

switch (cor) {
  case "vermelho":
    console.log("Pare!");
    break;
  case "amarelo":
    console.log("Atenção!");
    break;
  case "verde":
    console.log("Siga!");
    break;
  default:
    console.log("Cor inválida");
}

// ❌ MAU USO DO SWITCH: Intervalos/comparações complexas
// NÃO funciona bem:
const nota = 8;
switch (
  nota // ❌ Não use assim!
) {
  case nota >= 9:
    console.log("A");
    break;
  // ...
}

// ✅ USE IF-ELSE para intervalos:
if (nota >= 9) {
  console.log("A");
} else if (nota >= 7) {
  console.log("B");
} else if (nota >= 5) {
  console.log("C");
} else {
  console.log("D");
}
```

### 5.6: Exemplos Práticos Completos

```javascript
// Sistema de menu de restaurante
const opcaoMenu = 3;

console.log("=== MENU DO RESTAURANTE ===");
console.log("1 - Entrada");
console.log("2 - Prato Principal");
console.log("3 - Sobremesa");
console.log("4 - Bebida");
console.log("5 - Sair");
console.log("===========================");

switch (opcaoMenu) {
  case 1:
    console.log("\nENTRADAS DISPONÍVEIS:");
    console.log("- Salada Caesar");
    console.log("- Bruschetta");
    console.log("- Sopa do dia");
    break;
  case 2:
    console.log("\nPRATOS PRINCIPAIS:");
    console.log("- File mignon");
    console.log("- Salmão grelhado");
    console.log("- Risoto de funghi");
    break;
  case 3:
    console.log("\nSOBREMESAS:");
    console.log("- Petit gateau");
    console.log("- Tiramisu");
    console.log("- Sorvete");
    break;
  case 4:
    console.log("\nBEBIDAS:");
    console.log("- Sucos naturais");
    console.log("- Refrigerantes");
    console.log("- Vinhos");
    break;
  case 5:
    console.log("\nObrigado pela visita!");
    break;
  default:
    console.log("\n❌ Opção inválida!");
    console.log("Por favor, escolha entre 1 e 5");
}

// Sistema de classificação de produtos
const categoria = "eletronicos";
const precoProduto = 1500.0;

switch (categoria) {
  case "eletronicos":
    console.log("Categoria: Eletrônicos");
    console.log("Garantia: 12 meses");
    console.log("Troca: 30 dias");
    if (precoProduto > 1000) {
      console.log("🎁 Frete GRÁTIS!");
    }
    break;
  case "livros":
    console.log("Categoria: Livros");
    console.log("Garantia: Não aplicável");
    console.log("Troca: 7 dias");
    break;
  case "roupas":
    console.log("Categoria: Roupas");
    console.log("Garantia: 90 dias");
    console.log("Troca: 30 dias");
    break;
  case "alimentos":
    console.log("Categoria: Alimentos");
    console.log("Garantia: Vide validade");
    console.log("Troca: Não permitida");
    break;
  default:
    console.log("Categoria não encontrada");
}
```

---

## 🎓 Parte 6: Exercícios Práticos

### Exercício 1: Verificador de Número ⭐

**Objetivo:** Praticar if-else básico.

**Tarefa:**

```javascript
const numero = 15;

// Verifique se o número é:
// - Positivo, negativo ou zero
// - Par ou ímpar (se não for zero)

// Exemplo de saída esperada:
// "O número 15 é positivo e ímpar"
```

---

### Exercício 2: Calculadora de Média ⭐⭐

**Objetivo:** Usar if-else-if para classificação.

**Tarefa:**

```javascript
const nota1 = 7.5;
const nota2 = 8.0;
const nota3 = 6.5;

// 1. Calcule a média
// 2. Classifique:
//    - Média >= 9: "Excelente"
//    - Média >= 7: "Bom"
//    - Média >= 5: "Regular"
//    - Média < 5: "Insuficiente"
// 3. Exiba média e classificação
```

---

### Exercício 3: Sistema de Login ⭐⭐

**Objetivo:** Validar múltiplas condições.

**Tarefa:**

```javascript
const usuarioCadastrado = "admin";
const senhaCadastrada = "123456";

const usuarioDigitado = "admin";
const senhaDigitada = "123456";

// Verifique:
// - Se usuário E senha estão corretos: "Login realizado"
// - Se apenas usuário incorreto: "Usuário não encontrado"
// - Se apenas senha incorreta: "Senha incorreta"
// - Se ambos incorretos: "Usuário e senha incorretos"
```

---

### Exercício 4: Conversor de Conceitos ⭐⭐

**Objetivo:** Praticar operador ternário.

**Tarefa:**

```javascript
const nota = 8.5;

// Use operador ternário para:
// 1. Definir se aprovado ou reprovado (nota >= 7)
// 2. Definir conceito ("Ótimo" se >= 9, "Bom" caso contrário)
// 3. Exiba ambos os resultados
```

---

### Exercício 5: Calculadora com Switch ⭐⭐

**Objetivo:** Implementar operações com switch.

**Tarefa:**

```javascript
const numero1 = 10;
const numero2 = 5;
const operacao = "+"; // pode ser: +, -, *, /

// Use switch para realizar a operação escolhida
// Exiba o resultado formatado
// Exemplo: "10 + 5 = 15"
```

---

### Exercício 6: Classificador de Idade ⭐⭐

**Objetivo:** Usar if-else-if completo.

**Tarefa:**

```javascript
const idade = 15;

// Classifique em:
// 0-2: Bebê
// 3-11: Criança
// 12-17: Adolescente
// 18-59: Adulto
// 60+: Idoso

// Exiba também se pode:
// - Votar (>= 16)
// - Tirar CNH (>= 18)
// - Aposentar (>= 60)
```

---

### Exercício 7: Sistema de Descontos ⭐⭐⭐

**Objetivo:** Combinar condições complexas.

**Tarefa:**

```javascript
const valorCompra = 250.0;
const quantidadeItens = 3;
const ehPrimeiraCompra = false;
const clienteVIP = true;

// Regras de desconto:
// - Primeira compra: 15% de desconto
// - Cliente VIP: 20% de desconto
// - Compra > 200: 10% de desconto
// - Mais de 5 itens: 5% adicional
// (descontos não são cumulativos, use o maior)

// Calcule e exiba:
// - Valor original
// - Desconto aplicado (%)
// - Valor do desconto (R$)
// - Valor final
```

---

### Exercício 8: Validador de Senha ⭐⭐⭐

**Objetivo:** Validar múltiplos critérios.

**Tarefa:**

```javascript
const senha = "Senha123";

// Critérios de validação:
// - Tamanho entre 8 e 20 caracteres
// - (Assuma que contém letra maiúscula)
// - (Assuma que contém letra minúscula)
// - (Assuma que contém número)

const tamanho = senha.length;
const temMaiuscula = true; // simplificação
const temMinuscula = true; // simplificação
const temNumero = true; // simplificação

// Verifique cada critério e exiba:
// ✓ ou ✗ para cada um
// "Senha válida" ou "Senha inválida" no final
```

---

### Exercício 9: Conversor de Notas ⭐⭐⭐

**Objetivo:** Usar switch com strings.

**Tarefa:**

```javascript
const conceito = "B";

// Converta conceito em nota numérica:
// A: 10
// B: 8
// C: 6
// D: 4
// F: 0

// Use switch
// Exiba: "Conceito B equivale a nota 8"
```

---

### Exercício 10: Estacionamento Inteligente ⭐⭐⭐

**Objetivo:** Projeto integrador.

**Tarefa:**

```javascript
const tipoVeiculo = "carro"; // carro, moto, caminhao
const horasEstacionado = 3;
const ehMensalista = false;
const diaAtual = "sábado";

// Tabela de preços por hora:
// Moto: R$ 2,00
// Carro: R$ 5,00
// Caminhão: R$ 10,00

// Regras:
// - Mensalista não paga
// - Sábado e domingo: 50% de desconto
// - Primeira hora: sempre grátis (não mensalista)
// - Acima de 5 horas: 20% de desconto no total

// Calcule e exiba tudo detalhadamente
```

---

## Parte 7: Desafios Avançados (Opcional)

### Desafio 1: Jogo de Pedra, Papel e Tesoura 🔥🔥

```javascript
const jogador1 = "pedra"; // pedra, papel ou tesoura
const jogador2 = "tesoura";

// Regras:
// - Pedra ganha de tesoura
// - Tesoura ganha de papel
// - Papel ganha de pedra
// - Mesmo valor: empate

// Use if-else ou switch para determinar vencedor
// Exiba resultado formatado
```

---

### Desafio 2: Calculadora de Imposto de Renda 🔥🔥🔥

```javascript
const salarioBruto = 5000.0;

// Tabelas do IR 2024 (simplificada):
// Até 2112: isento
// 2112.01 a 2826: 7.5%
// 2826.01 a 3751: 15%
// 3751.01 a 4664: 22.5%
// Acima de 4664: 27.5%

// Calcule:
// - Alíquota aplicada
// - Valor do imposto
// - Salário líquido
// Exiba tudo formatado
```

---

### Desafio 3: Sistema de Avaliação de Crédito 🔥🔥🔥

```javascript
const score = 650;
const rendaMensal = 4000.0;
const idade = 35;
const temRestricao = false;
const valorEmprestimo = 30000.0;

// Classificação de score:
// 0-300: Muito ruim
// 301-500: Ruim
// 501-700: Regular
// 701-900: Bom
// 901-1000: Excelente

// Regras de aprovação:
// - Score mínimo: 500
// - Idade: 18-70
// - Renda mínima: R$ 2000
// - Sem restrição no CPF
// - Empréstimo não pode ser > 10x a renda

// Crie análise completa com:
// - Verificação de cada critério
// - Classificação do score
// - Decisão final (aprovado/negado)
// - Motivo se negado
```

---

## Parte 8: Projeto da Semana

### 🎯 Sistema de Classificação de Filmes

**Objetivo:** Criar um sistema completo de recomendação de filmes.

**Requisitos:**

```javascript
// ===== DADOS DO USUÁRIO =====
const nomeUsuario = "Maria Silva";
const idadeUsuario = 16;
const generoFavorito = "acao"; // acao, comedia, drama, terror, romance

// ===== DADOS DO FILME =====
const nomeFilme = "Velozes e Furiosos";
const classificacaoEtaria = 14; // anos
const generoFilme = "acao";
const duracaoMinutos = 140;
const notaIMDb = 7.5;
const anoLancamento = 2023;

// ===== ANÁLISE DO SISTEMA =====

console.log("========================================");
console.log("   SISTEMA DE RECOMENDAÇÃO DE FILMES   ");
console.log("========================================");

// 1. VERIFICAÇÃO DE IDADE
console.log("\n--- VERIFICAÇÃO DE IDADE ---");
// Implemente aqui

// 2. COMPATIBILIDADE DE GÊNERO
console.log("\n--- COMPATIBILIDADE DE GÊNERO ---");
// Implemente aqui

// 3. CLASSIFICAÇÃO POR DURAÇÃO
console.log("\n--- DURAÇÃO DO FILME ---");
// Curto: < 90min
// Médio: 90-150min
// Longo: > 150min
// Implemente aqui

// 4. AVALIAÇÃO DA NOTA
console.log("\n--- AVALIAÇÃO ---");
// >= 9: Obra-prima
// >= 8: Excelente
// >= 7: Muito bom
// >= 6: Bom
// >= 5: Regular
// < 5: Ruim
// Implemente aqui

// 5. NOVIDADE
console.log("\n--- NOVIDADE ---");
const anoAtual = 2025;
// Se lançou este ano ou ano passado: "Lançamento recente"
// Se 2-5 anos: "Filme recente"
// Se > 5 anos: "Clássico"
// Implemente aqui

// 6. RECOMENDAÇÃO FINAL
console.log("\n========================================");
console.log("          RECOMENDAÇÃO FINAL            ");
console.log("========================================");

// Lógica de recomendação:
// - Se menor de idade E filme maior que sua idade: NÃO recomendado
// - Se gênero diferente: Recomendação moderada
// - Se gênero igual E nota >= 7: Altamente recomendado
// - Se nota < 6: Não recomendado
// Implemente aqui

// 7. EXTRAS
// Adicione informações extras como:
// - Tempo disponível do usuário
// - Se deve assistir sozinho ou com família
// - Melhor horário (matinê, vespertino, noturno)
```

**Critérios de avaliação:**

- [ ] Usa if-else-if adequadamente
- [ ] Implementa pelo menos um switch
- [ ] Usa operador ternário em algum lugar
- [ ] Validação de idade funciona corretamente
- [ ] Lógica de recomendação está clara
- [ ] Código bem comentado
- [ ] Saída formatada e legível
- [ ] Trata todos os casos (inclusive inválidos)

**Bônus:**

- Adicione mais critérios de recomendação
- Crie um sistema de pontuação
- Faça recomendações de filmes similares

---

## Parte 9: Checklist de Aprendizado

Ao final da Semana 3, você deve ser capaz de:

- [ ] Usar if para executar código condicionalmente
- [ ] Implementar if-else para duas alternativas
- [ ] Usar if-else-if para múltiplas condições
- [ ] Entender quando usar cada estrutura
- [ ] Criar condicionais aninhadas
- [ ] Usar operador ternário para casos simples
- [ ] Diferenciar ternário de if-else tradicional
- [ ] Implementar switch case corretamente
- [ ] Usar break adequadamente no switch
- [ ] Saber quando usar switch vs if-else
- [ ] Combinar estruturas condicionais
- [ ] Resolver problemas com lógica complexa

---

## Parte 10: Troubleshooting

### Problema 1: If não executa quando deveria

```javascript
const idade = "18"; // string!

if (idade >= 18) {
  // comparação com tipo errado
  console.log("Maior de idade");
}

// Solução: Sempre use === e verifique tipos
if (idade === 18) {
  // ou converta: Number(idade)
  console.log("Maior de idade");
}
```

### Problema 2: Switch não funciona

```javascript
const opcao = 1;

switch (opcao) {
  case 1:
    console.log("Um");
  // ❌ Esqueceu o break!
  case 2:
    console.log("Dois");
    break;
}
// Saída: "Um" e "Dois" (fall-through)

// Solução: Sempre use break
```

### Problema 3: Else if na ordem errada

```javascript
const nota = 9;

// ❌ ERRADO - ordem importa!
if (nota >= 5) {
  console.log("Regular"); // Executa este!
} else if (nota >= 7) {
  console.log("Bom"); // Nunca chega aqui
} else if (nota >= 9) {
  console.log("Excelente");
}

// ✅ CORRETO - do mais específico ao mais geral
if (nota >= 9) {
  console.log("Excelente");
} else if (nota >= 7) {
  console.log("Bom");
} else if (nota >= 5) {
  console.log("Regular");
}
```

### Problema 4: Operador ternário complexo demais

```javascript
// ❌ Difícil de ler
const resultado = a > b ? (c > d ? "x" : c > e ? "y" : "z") : "w";

// ✅ Use if-else para lógica complexa
let resultado;
if (a > b) {
  if (c > d) {
    resultado = "x";
  } else if (c > e) {
    resultado = "y";
  } else {
    resultado = "z";
  }
} else {
  resultado = "w";
}
```

---

## Parte 11: Boas Práticas

### ✅ FAÇA:

1. **Use === em vez de ==**

```javascript
if (valor === 10) {
} // ✅
```

2. **Agrupe condições relacionadas com parênteses**

```javascript
if ((idade >= 18 && temCNH) || ehInstrutor) {
}
```

3. **Mantenha condições simples e legíveis**

```javascript
const podeVotar = idade >= 16;
if (podeVotar) {
}
```

4. **Use early return para simplificar**

```javascript
// ❌ Aninhamento profundo
if (usuario) {
  if (usuario.ativo) {
    if (usuario.idade >= 18) {
      // código
    }
  }
}

// ✅ Melhor
if (!usuario) return;
if (!usuario.ativo) return;
if (usuario.idade < 18) return;
// código
```

5. **Comente lógicas complexas**

```javascript
// Verifica se cliente tem direito a desconto VIP
if ((totalCompras > 1000 && tempoCliente > 12) || indicacaoGerente) {
  aplicarDescontoVIP();
}
```

### ❌ EVITE:

1. **Comparações desnecessárias com true/false**

```javascript
// ❌
if (isAtivo === true) {
}

// ✅
if (isAtivo) {
}
```

2. **Else desnecessário**

```javascript
// ❌
if (condicao) {
  return true;
} else {
  return false;
}

// ✅
return condicao;
```

3. **Condições muito longas em uma linha**

```javascript
// ❌
if (a && b && c && d && e && f && g) {
}

// ✅
const todasCondicoesAtendidas = a && b && c && d && e && f && g;
if (todasCondicoesAtendidas) {
}
```

---

## Recursos Adicionais

### Documentação:

- **MDN - if...else**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/if...else
- **MDN - switch**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/switch
- **MDN - Operador Condicional**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Conditional_Operator

### Prática Online:

- **JavaScript Visualizer**: pythontutor.com/javascript.html
- **Exercícios**: exercism.org

---

## Preparação para Semana 4

Na próxima semana você aprenderá:

- ✨ Loops (for, while, do-while)
- ✨ Iteração sobre sequências
- ✨ Break e continue
- ✨ Padrões de repetição

**Pré-requisito:** Domine as estruturas condicionais desta semana!

---

**Professor:** Marcelo Damasceno de Melo

**Curso:** Introdução ao JavaScript

**Semana:** 3 de 8

**Próxima aula:** Estruturas de Repetição

---
