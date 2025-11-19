# Roteiro de Estudos: Introdução ao JavaScript - Semana 5

## Objetivo da Semana

Dominar o conceito de arrays (listas) em JavaScript, aprendendo a armazenar, acessar, modificar e manipular coleções de dados de forma eficiente, essencial para trabalhar com conjuntos de informações no desenvolvimento de aplicações.

---

## ⚠️ PRÉ-REQUISITOS OBRIGATÓRIOS

**ATENÇÃO:** Antes de iniciar esta semana, você DEVE dominar:

- ✅ Variáveis (`let` e `const`)
- ✅ Tipos de dados primitivos
- ✅ Operadores (aritméticos, comparação, lógicos)
- ✅ Estruturas condicionais (if, else, switch)
- ✅ Loops (for, while, do-while)
- ✅ Incremento e decremento (++, --)

**Se ainda tem dúvidas:** Revise as Semanas 1-4 antes de prosseguir!

---

## Parte 1: Introdução aos Arrays

### 1.1: O que são Arrays?

Um **array** (ou lista) é uma estrutura de dados que armazena **múltiplos valores** em uma **única variável**.

**Analogia da vida real:**

- Lista de compras (vários itens)
- Agenda de contatos (vários nomes)
- Playlist de músicas (várias músicas)
- Estante de livros (vários livros)

**Por que usar arrays?**

```javascript
// ❌ SEM ARRAY - Código repetitivo
const aluno1 = "João";
const aluno2 = "Maria";
const aluno3 = "Pedro";
const aluno4 = "Ana";
const aluno5 = "Carlos";
// E se forem 100 alunos?

// ✅ COM ARRAY - Organizado e eficiente
const alunos = ["João", "Maria", "Pedro", "Ana", "Carlos"];
```

### 1.2: Criando Arrays

```javascript
// Método 1: Notação literal [] (RECOMENDADO)
const numeros = [1, 2, 3, 4, 5];
const frutas = ["maçã", "banana", "laranja"];
const valores = [10, 20, 30, 40, 50];

// Método 2: Construtor Array() (menos comum)
const cores = new Array("vermelho", "azul", "verde");

// Array vazio
const listaVazia = [];

// Array com tipos diferentes (possível, mas evite)
const misto = [1, "texto", true, 3.14]; // Funciona, mas não é boa prática

// Array com espaços reservados
const espacos = new Array(5); // Array com 5 posições vazias
console.log(espacos.length); // 5
```

### 1.3: Índices de Arrays

Arrays usam **índices numéricos** começando do **zero** para acessar elementos.

```javascript
const frutas = ["maçã", "banana", "laranja", "uva", "manga"];

// Índices:      0        1         2         3       4

console.log(frutas[0]); // "maçã" (primeiro elemento)
console.log(frutas[1]); // "banana"
console.log(frutas[2]); // "laranja"
console.log(frutas[4]); // "manga" (último elemento)

// Índice inválido retorna undefined
console.log(frutas[10]); // undefined

// Visualização:
// Posição:  0      1        2         3      4
// Valor:   maçã  banana  laranja    uva   manga
```

### 1.4: Propriedade Length

A propriedade `.length` retorna o **número de elementos** no array.

```javascript
const numeros = [10, 20, 30, 40, 50];

console.log(numeros.length); // 5

// Último elemento (sempre length - 1)
console.log(numeros[numeros.length - 1]); // 50

// Array vazio
const vazio = [];
console.log(vazio.length); // 0

// Útil em loops
const frutas = ["maçã", "banana", "laranja"];

for (let i = 0; i < frutas.length; i++) {
  console.log(`Fruta ${i + 1}: ${frutas[i]}`);
}
// Saída:
// Fruta 1: maçã
// Fruta 2: banana
// Fruta 3: laranja
```

---

## Parte 2: Acessando e Modificando Arrays

### 2.1: Lendo Elementos

```javascript
const notas = [7.5, 8.0, 6.5, 9.0, 7.0];

// Acessar elementos individuais
const primeiraNota = notas[0];
const segundaNota = notas[1];
const ultimaNota = notas[notas.length - 1];

console.log("Primeira nota:", primeiraNota); // 7.5
console.log("Última nota:", ultimaNota); // 7.0

// Usar em cálculos
const soma = notas[0] + notas[1] + notas[2];
console.log("Soma das 3 primeiras:", soma); // 22.0

// Verificar valores
if (notas[0] >= 7) {
  console.log("Primeira nota aprovada!");
}
```

### 2.2: Modificando Elementos

```javascript
const frutas = ["maçã", "banana", "laranja"];

console.log("Antes:", frutas); // ["maçã", "banana", "laranja"]

// Modificar elemento existente
frutas[1] = "morango";
console.log("Depois:", frutas); // ["maçã", "morango", "laranja"]

// Modificar múltiplos elementos
frutas[0] = "abacaxi";
frutas[2] = "uva";
console.log("Final:", frutas); // ["abacaxi", "morango", "uva"]

// Exemplo prático: Atualizar notas
const notas = [7.0, 6.0, 8.0];
console.log("Notas originais:", notas);

// Aluno fez recuperação (posição 1)
notas[1] = 7.5;
console.log("Após recuperação:", notas); // [7.0, 7.5, 8.0]
```

### 2.3: Iterando sobre Arrays

```javascript
// Exemplo 1: Exibir todos os elementos
const alunos = ["Ana", "Bruno", "Carlos", "Diana"];

console.log("=== LISTA DE ALUNOS ===");
for (let i = 0; i < alunos.length; i++) {
  console.log(`${i + 1}. ${alunos[i]}`);
}
// Saída:
// 1. Ana
// 2. Bruno
// 3. Carlos
// 4. Diana

// Exemplo 2: Calcular soma
const numeros = [10, 20, 30, 40, 50];
let soma = 0;

for (let i = 0; i < numeros.length; i++) {
  soma += numeros[i];
}

console.log("Soma total:", soma); // 150

// Exemplo 3: Calcular média
const notas = [7.5, 8.0, 6.5, 9.0, 7.0];
let somaNotas = 0;

for (let i = 0; i < notas.length; i++) {
  somaNotas += notas[i];
}

const media = somaNotas / notas.length;
console.log("Média:", media.toFixed(2)); // 7.60

// Exemplo 4: Encontrar maior valor
const valores = [45, 23, 67, 12, 89, 34];
let maior = valores[0]; // Começa com o primeiro

for (let i = 1; i < valores.length; i++) {
  if (valores[i] > maior) {
    maior = valores[i];
  }
}

console.log("Maior valor:", maior); // 89

// Exemplo 5: Contar elementos específicos
const temperaturas = [25, 30, 28, 35, 32, 27, 38];
let diasQuentes = 0; // temperatura > 30

for (let i = 0; i < temperaturas.length; i++) {
  if (temperaturas[i] > 30) {
    diasQuentes++;
  }
}

console.log("Dias com temperatura > 30°C:", diasQuentes); // 3
```

---

## Parte 3: Métodos de Manipulação de Arrays

### 3.1: Adicionar Elementos

#### A) push() - Adiciona no FINAL

```javascript
const frutas = ["maçã", "banana"];

console.log("Antes:", frutas); // ["maçã", "banana"]

frutas.push("laranja");
console.log("Depois:", frutas); // ["maçã", "banana", "laranja"]

// Pode adicionar múltiplos elementos
frutas.push("uva", "manga");
console.log("Final:", frutas); // ["maçã", "banana", "laranja", "uva", "manga"]

// push() retorna o novo tamanho
const novoTamanho = frutas.push("abacaxi");
console.log("Novo tamanho:", novoTamanho); // 6

// Exemplo prático: Carrinho de compras
const carrinho = [];
console.log("Carrinho vazio:", carrinho);

carrinho.push("Notebook");
carrinho.push("Mouse");
carrinho.push("Teclado");
console.log("Carrinho:", carrinho); // ["Notebook", "Mouse", "Teclado"]
```

#### B) unshift() - Adiciona no INÍCIO

```javascript
const numeros = [2, 3, 4];

console.log("Antes:", numeros); // [2, 3, 4]

numeros.unshift(1);
console.log("Depois:", numeros); // [1, 2, 3, 4]

// Pode adicionar múltiplos elementos
numeros.unshift(-1, 0);
console.log("Final:", numeros); // [-1, 0, 1, 2, 3, 4]

// Exemplo prático: Fila de prioridade
const fila = ["João", "Maria", "Pedro"];
console.log("Fila normal:", fila);

fila.unshift("VIP: Carlos"); // VIP entra na frente
console.log("Com VIP:", fila); // ["VIP: Carlos", "João", "Maria", "Pedro"]
```

### 3.2: Remover Elementos

#### A) pop() - Remove do FINAL

```javascript
const frutas = ["maçã", "banana", "laranja"];

console.log("Antes:", frutas); // ["maçã", "banana", "laranja"]

const removida = frutas.pop();
console.log("Removida:", removida); // "laranja"
console.log("Depois:", frutas); // ["maçã", "banana"]

// Remove até esvaziar
frutas.pop(); // remove "banana"
frutas.pop(); // remove "maçã"
console.log("Vazio:", frutas); // []

// Exemplo prático: Desfazer ações
const acoes = ["abrir", "editar", "salvar"];
console.log("Ações:", acoes);

const ultimaAcao = acoes.pop();
console.log("Desfazendo:", ultimaAcao); // "salvar"
console.log("Ações restantes:", acoes); // ["abrir", "editar"]
```

#### B) shift() - Remove do INÍCIO

```javascript
const numeros = [1, 2, 3, 4, 5];

console.log("Antes:", numeros); // [1, 2, 3, 4, 5]

const removido = numeros.shift();
console.log("Removido:", removido); // 1
console.log("Depois:", numeros); // [2, 3, 4, 5]

// Exemplo prático: Fila de atendimento
const fila = ["João", "Maria", "Pedro", "Ana"];
console.log("Fila:", fila);

const atendido = fila.shift();
console.log(`Atendendo: ${atendido}`);
console.log("Fila atualizada:", fila); // ["Maria", "Pedro", "Ana"]
```

### 3.3: Outros Métodos Importantes

#### A) splice() - Adiciona/Remove em qualquer posição

```javascript
// Sintaxe: array.splice(índice, quantosRemover, novosElementos...)

// Exemplo 1: Remover elementos
const numeros = [1, 2, 3, 4, 5];
numeros.splice(2, 1); // Remove 1 elemento na posição 2
console.log(numeros); // [1, 2, 4, 5]

// Exemplo 2: Adicionar elementos
const frutas = ["maçã", "laranja"];
frutas.splice(1, 0, "banana"); // Na posição 1, remove 0, adiciona "banana"
console.log(frutas); // ["maçã", "banana", "laranja"]

// Exemplo 3: Substituir elementos
const cores = ["vermelho", "azul", "verde"];
cores.splice(1, 1, "amarelo"); // Remove 1 na posição 1 e adiciona "amarelo"
console.log(cores); // ["vermelho", "amarelo", "verde"]

// Exemplo 4: Remover múltiplos
const letras = ["a", "b", "c", "d", "e"];
letras.splice(1, 3); // Remove 3 elementos a partir da posição 1
console.log(letras); // ["a", "e"]
```

#### B) slice() - Copia parte do array (NÃO modifica original)

```javascript
const numeros = [1, 2, 3, 4, 5];

// slice(início, fim) - fim não é incluído
const parte = numeros.slice(1, 4);
console.log("Parte:", parte); // [2, 3, 4]
console.log("Original:", numeros); // [1, 2, 3, 4, 5] (não mudou!)

// slice(início) - do início até o fim
const doMeioAoFim = numeros.slice(2);
console.log(doMeioAoFim); // [3, 4, 5]

// slice() - copia tudo
const copia = numeros.slice();
console.log(copia); // [1, 2, 3, 4, 5]

// Índices negativos (conta de trás pra frente)
const ultimos = numeros.slice(-2);
console.log(ultimos); // [4, 5]
```

#### C) indexOf() - Encontra posição do elemento

```javascript
const frutas = ["maçã", "banana", "laranja", "banana"];

// Encontra primeira ocorrência
const posicao = frutas.indexOf("banana");
console.log("Posição de banana:", posicao); // 1

// Elemento não existe retorna -1
const naoExiste = frutas.indexOf("uva");
console.log("Posição de uva:", naoExiste); // -1

// Verificar se elemento existe
if (frutas.indexOf("maçã") !== -1) {
  console.log("Maçã está na lista!");
}

// Buscar a partir de uma posição
const segundaBanana = frutas.indexOf("banana", 2);
console.log("Segunda banana:", segundaBanana); // 3

// Exemplo prático: Verificar cadastro
const usuariosCadastrados = ["joao123", "maria456", "pedro789"];
const novoUsuario = "maria456";

if (usuariosCadastrados.indexOf(novoUsuario) !== -1) {
  console.log("❌ Usuário já cadastrado!");
} else {
  console.log("✓ Usuário disponível");
}
```

#### D) includes() - Verifica se elemento existe

```javascript
const numeros = [1, 2, 3, 4, 5];

// Retorna true ou false
console.log(numeros.includes(3)); // true
console.log(numeros.includes(10)); // false

// Exemplo prático: Verificar permissões
const permissoes = ["ler", "escrever", "deletar"];

if (permissoes.includes("deletar")) {
  console.log("✓ Usuário pode deletar arquivos");
} else {
  console.log("❌ Sem permissão para deletar");
}

// Verificar item no carrinho
const carrinho = ["Notebook", "Mouse", "Teclado"];
const produto = "Mouse";

if (carrinho.includes(produto)) {
  console.log(`${produto} já está no carrinho`);
}
```

#### E) reverse() - Inverte a ordem (MODIFICA o original)

```javascript
const numeros = [1, 2, 3, 4, 5];

console.log("Antes:", numeros); // [1, 2, 3, 4, 5]

numeros.reverse();
console.log("Depois:", numeros); // [5, 4, 3, 2, 1]

// Exemplo prático: Contagem regressiva
const contagem = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
contagem.reverse();

console.log("Contagem regressiva:");
for (let i = 0; i < contagem.length; i++) {
  console.log(contagem[i]);
}
// Saída: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

#### F) sort() - Ordena o array (MODIFICA o original)

```javascript
// Ordenação alfabética (strings)
const frutas = ["banana", "maçã", "laranja", "abacaxi"];
frutas.sort();
console.log(frutas); // ["abacaxi", "banana", "laranja", "maçã"]

// ⚠️ CUIDADO: sort() converte para string!
const numeros = [10, 5, 40, 25, 1000];
numeros.sort();
console.log(numeros); // [10, 1000, 25, 40, 5] ❌ Ordem errada!

// ✅ Para números, use função de comparação
const valores = [10, 5, 40, 25, 1000];
valores.sort(function (a, b) {
  return a - b; // Ordem crescente
});
console.log(valores); // [5, 10, 25, 40, 1000] ✓

// Ordem decrescente
valores.sort(function (a, b) {
  return b - a;
});
console.log(valores); // [1000, 40, 25, 10, 5] ✓
```

#### G) join() - Converte array em string

```javascript
const palavras = ["JavaScript", "é", "incrível"];

// Junta com espaço
const frase = palavras.join(" ");
console.log(frase); // "JavaScript é incrível"

// Junta com outro separador
const lista = ["maçã", "banana", "laranja"];
console.log(lista.join(", ")); // "maçã, banana, laranja"
console.log(lista.join(" - ")); // "maçã - banana - laranja"
console.log(lista.join("")); // "maçãbanana laranja"

// Exemplo prático: Criar caminho
const pastas = ["home", "usuario", "documentos", "projeto"];
const caminho = pastas.join("/");
console.log(caminho); // "home/usuario/documentos/projeto"
```

### 3.4: Resumo Visual dos Métodos

```javascript
const arr = [1, 2, 3];

// ADICIONAR:
arr.push(4); // [1, 2, 3, 4]     - adiciona no fim
arr.unshift(0); // [0, 1, 2, 3, 4]  - adiciona no início

// REMOVER:
arr.pop(); // [0, 1, 2, 3]     - remove do fim
arr.shift(); // [1, 2, 3]        - remove do início

// BUSCAR:
arr.indexOf(2); // 1                - retorna índice
arr.includes(2); // true             - retorna boolean

// COPIAR:
arr.slice(0, 2); // [1, 2]           - copia parte

// MODIFICAR:
arr.splice(1, 1); // [1, 3]           - remove/adiciona
arr.reverse(); // [3, 1]           - inverte
arr.sort(); // [1, 3]           - ordena

// CONVERTER:
arr.join("-"); // "1-3"            - array → string
```

---

## Parte 4: Arrays Multidimensionais

### 4.1: Arrays dentro de Arrays

Arrays podem conter outros arrays, criando estruturas bidimensionais (matrizes).

```javascript
// Array bidimensional (matriz)
const matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

// Acessar elementos
console.log(matriz[0]); // [1, 2, 3] (primeira linha)
console.log(matriz[0][0]); // 1 (linha 0, coluna 0)
console.log(matriz[1][2]); // 6 (linha 1, coluna 2)
console.log(matriz[2][1]); // 8 (linha 2, coluna 1)

// Visualização:
//        col0  col1  col2
// lin0:   1     2     3
// lin1:   4     5     6
// lin2:   7     8     9
```

### 4.2: Exemplos Práticos

```javascript
// Exemplo 1: Tabela de produtos
const produtos = [
  ["Notebook", 2500.0, 5],
  ["Mouse", 50.0, 20],
  ["Teclado", 150.0, 15],
];

// Exibir tabela
console.log("PRODUTO\t\tPREÇO\t\tESTOQUE");
console.log("----------------------------------------");

for (let i = 0; i < produtos.length; i++) {
  const nome = produtos[i][0];
  const preco = produtos[i][1];
  const estoque = produtos[i][2];

  console.log(`${nome}\t\tR$ ${preco}\t\t${estoque} un`);
}

// Exemplo 2: Jogo da velha
const jogoVelha = [
  ["X", "O", "X"],
  ["O", "X", "O"],
  ["O", "X", "X"],
];

// Exibir tabuleiro
console.log("\nJOGO DA VELHA:");
for (let i = 0; i < jogoVelha.length; i++) {
  console.log(jogoVelha[i].join(" | "));
  if (i < 2) console.log("---------");
}
// Saída:
// X | O | X
// ---------
// O | X | O
// ---------
// O | X | X

// Exemplo 3: Notas de alunos
const turma = [
  ["Ana", 7.5, 8.0, 6.5],
  ["Bruno", 9.0, 8.5, 9.5],
  ["Carlos", 6.0, 7.0, 6.5],
];

console.log("\nBOLETIM DA TURMA:");
console.log("ALUNO\t\tN1\tN2\tN3\tMÉDIA");
console.log("--------------------------------------------");

for (let i = 0; i < turma.length; i++) {
  const nome = turma[i][0];
  const nota1 = turma[i][1];
  const nota2 = turma[i][2];
  const nota3 = turma[i][3];
  const media = ((nota1 + nota2 + nota3) / 3).toFixed(2);

  console.log(`${nome}\t\t${nota1}\t${nota2}\t${nota3}\t${media}`);
}

// Exemplo 4: Soma de matriz
const numeros = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

let soma = 0;

for (let i = 0; i < numeros.length; i++) {
  for (let j = 0; j < numeros[i].length; j++) {
    soma += numeros[i][j];
  }
}

console.log("\nSoma de todos os elementos:", soma); // 45
```

---

## 🎓 Parte 5: Exercícios Práticos

### Exercício 1: Criação e Acesso ⭐

**Objetivo:** Praticar criação e acesso a arrays.

**Tarefa:**

```javascript
// 1. Crie um array com 5 nomes de frutas
// 2. Exiba a primeira fruta
// 3. Exiba a última fruta
// 4. Exiba o tamanho do array
// 5. Exiba a fruta do meio (posição 2)
```

---

### Exercício 2: Soma de Array ⭐

**Objetivo:** Iterar e acumular valores.

**Tarefa:**

```javascript
const numeros = [5, 10, 15, 20, 25];

// Calcule a soma de todos os números
// Use um loop for
// Exiba o resultado
```

---

### Exercício 3: Maior e Menor ⭐⭐

**Objetivo:** Encontrar valores extremos.

**Tarefa:**

```javascript
const temperaturas = [22, 18, 25, 30, 19, 27, 21];

// Encontre:
// - A maior temperatura
// - A menor temperatura
// - A temperatura média
// Use loops
```

---

### Exercício 4: Adicionar e Remover ⭐⭐

**Objetivo:** Praticar métodos de manipulação.

**Tarefa:**

```javascript
const tarefas = ["Estudar", "Fazer exercícios"];

// 1. Adicione "Ler livro" no final
// 2. Adicione "Acordar cedo" no início
// 3. Remova a última tarefa
// 4. Exiba o array final
// 5. Exiba o tamanho do array
```

---

### Exercício 5: Busca em Array ⭐⭐

**Objetivo:** Procurar elementos.

**Tarefa:**

```javascript
const alunos = ["João", "Maria", "Pedro", "Ana", "Carlos"];
const nomeBuscado = "Pedro";

// 1. Verifique se o nome está na lista (use indexOf ou includes)
// 2. Se estiver, exiba "Aluno encontrado na posição X"
// 3. Se não estiver, exiba "Aluno não encontrado"
```

---

### Exercício 6: Filtrar Pares ⭐⭐

**Objetivo:** Criar novo array baseado em condição.

**Tarefa:**

```javascript
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

// Crie um novo array apenas com os números PARES
// Use loop e push
// Exiba o array de pares
```

---

### Exercício 7: Aprovados e Reprovados ⭐⭐⭐

**Objetivo:** Classificar elementos.

**Tarefa:**

```javascript
const notas = [7.5, 4.0, 8.0, 5.5, 9.0, 3.5, 6.0, 7.0];

// Crie dois arrays:
// - aprovados (nota >= 7)
// - reprovados (nota < 7)
// Exiba quantos foram aprovados e reprovados
// Exiba ambos os arrays
```

---

### Exercício 8: Inverter Array ⭐⭐⭐

**Objetivo:** Manipular ordem sem usar reverse().

**Tarefa:**

```javascript
const original = [1, 2, 3, 4, 5];

// Crie um novo array com os elementos em ordem inversa
// NÃO use reverse()
// Use um loop
// Exiba o array invertido
```

---

### Exercício 9: Remover Duplicados ⭐⭐⭐

**Objetivo:** Criar array sem repetições.

**Tarefa:**

```javascript
const numeros = [1, 2, 2, 3, 4, 4, 5, 1, 6];

// Crie um novo array sem elementos duplicados
// Dica: use indexOf ou includes para verificar se já existe
// Exiba o array sem duplicados
```

---

### Exercício 10: Média de Turma ⭐⭐⭐

**Objetivo:** Trabalhar com arrays bidimensionais.

**Tarefa:**

```javascript
const turma = [
  ["Ana", 7.5, 8.0, 6.5],
  ["Bruno", 9.0, 8.5, 9.5],
  ["Carlos", 6.0, 7.0, 6.5],
  ["Diana", 8.0, 7.5, 8.5],
];

// Para cada aluno:
// 1. Calcule a média das 3 notas
// 2. Determine se está aprovado (média >= 7)
// 3. Exiba: "Nome: média - Status"
//
// No final, exiba:
// - Total de aprovados
// - Total de reprovados
// - Média geral da turma
```

---

## Parte 6: Desafios Avançados (Opcional)

### Desafio 1: Ordenação Simples (Bubble Sort) 🔥🔥🔥

```javascript
const numeros = [64, 34, 25, 12, 22, 11, 90];

// Implemente o algoritmo Bubble Sort SEM usar sort()
//
// Lógica:
// - Compare pares adjacentes
// - Se estiverem fora de ordem, troque
// - Repita até ordenar tudo
//
// Exemplo:
// [64, 34] → 64 > 34, troca → [34, 64]
// [64, 25] → 64 > 25, troca → [34, 25, 64]
// Continue...

// Seu código aqui
```

---

### Desafio 2: Rotacionar Array 🔥🔥

```javascript
const array = [1, 2, 3, 4, 5];
const posicoes = 2;

// Rotacione o array para a direita em N posições
// Exemplo: rotacionar 2 posições
// [1, 2, 3, 4, 5] → [4, 5, 1, 2, 3]
//
// Não use métodos prontos (só push, pop, etc.)
```

---

### Desafio 3: Matriz Transposta 🔥🔥🔥

```javascript
const matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

// Crie a matriz transposta (linhas viram colunas)
// Matriz original:     Matriz transposta:
// 1  2  3              1  4  7
// 4  5  6      →       2  5  8
// 7  8  9              3  6  9
```

---

### Desafio 4: Simulador de Fila de Banco 🔥🔥🔥

```javascript
// Crie um simulador de fila de banco que:
// 1. Adiciona clientes na fila (use push)
// 2. Atende o primeiro da fila (use shift)
// 3. Permite adicionar clientes prioritários no início (unshift)
// 4. Mostra o tamanho da fila
// 5. Mostra quem será o próximo a ser atendido
// 6. Lista todos na fila

const fila = [];

// Implemente as funções:
// - adicionarCliente(nome)
// - adicionarPrioritario(nome)
// - atenderProximo()
// - proximoNaFila()
// - tamanhoFila()
// - listarFila()

// Teste o sistema com pelo menos 10 operações
```

---

## Parte 7: Projeto da Semana

### 🎯 Sistema de Gerenciamento de Estoque

**Objetivo:** Criar um sistema completo de controle de estoque de uma loja.

**Requisitos:**

```javascript
// ===== ESTRUTURA DE DADOS =====
// Cada produto é um array: [id, nome, preço, quantidade]
const estoque = [
  [1, "Notebook", 2500.0, 10],
  [2, "Mouse", 50.0, 50],
  [3, "Teclado", 150.0, 30],
  [4, "Monitor", 800.0, 15],
  [5, "Webcam", 200.0, 20],
];

console.log("========================================");
console.log("   SISTEMA DE GERENCIAMENTO DE ESTOQUE ");
console.log("========================================\n");

// ===== PARTE 1: RELATÓRIO COMPLETO DO ESTOQUE =====
console.log("--- ESTOQUE ATUAL ---\n");
console.log("ID\tPRODUTO\t\tPREÇO\t\tQTD\tTOTAL");
console.log("-----------------------------------------------------------");

let valorTotalEstoque = 0;
let quantidadeTotalItens = 0;

for (let i = 0; i < estoque.length; i++) {
  const id = estoque[i][0];
  const nome = estoque[i][1];
  const preco = estoque[i][2];
  const quantidade = estoque[i][3];
  const totalProduto = preco * quantidade;

  valorTotalEstoque += totalProduto;
  quantidadeTotalItens += quantidade;

  console.log(
    `${id}\t${nome}\t\tR$ ${preco.toFixed(
      2
    )}\t${quantidade}\tR$ ${totalProduto.toFixed(2)}`
  );
}

console.log("-----------------------------------------------------------");
console.log(`TOTAL DE ITENS: ${quantidadeTotalItens}`);
console.log(`VALOR TOTAL DO ESTOQUE: R$ ${valorTotalEstoque.toFixed(2)}\n`);

// ===== PARTE 2: PRODUTOS COM ESTOQUE BAIXO =====
console.log("--- ALERTA: ESTOQUE BAIXO (< 20 unidades) ---\n");

const estoqueBaixo = [];
const limiteBaixo = 20;

for (let i = 0; i < estoque.length; i++) {
  if (estoque[i][3] < limiteBaixo) {
    estoqueBaixo.push(estoque[i]);
  }
}

if (estoqueBaixo.length === 0) {
  console.log("✓ Todos os produtos com estoque adequado\n");
} else {
  for (let i = 0; i < estoqueBaixo.length; i++) {
    const nome = estoqueBaixo[i][1];
    const qtd = estoqueBaixo[i][3];
    console.log(`⚠️  ${nome}: apenas ${qtd} unidades`);
  }
  console.log("");
}

// ===== PARTE 3: PRODUTO MAIS CARO E MAIS BARATO =====
console.log("--- ANÁLISE DE PREÇOS ---\n");

let produtoMaisCaro = estoque[0];
let produtoMaisBarato = estoque[0];

for (let i = 1; i < estoque.length; i++) {
  if (estoque[i][2] > produtoMaisCaro[2]) {
    produtoMaisCaro = estoque[i];
  }
  if (estoque[i][2] < produtoMaisBarato[2]) {
    produtoMaisBarato = estoque[i];
  }
}

console.log(
  `Produto mais caro: ${produtoMaisCaro[1]} - R$ ${produtoMaisCaro[2].toFixed(
    2
  )}`
);
console.log(
  `Produto mais barato: ${
    produtoMaisBarato[1]
  } - R$ ${produtoMaisBarato[2].toFixed(2)}\n`
);

// ===== PARTE 4: SIMULAÇÃO DE VENDAS =====
console.log("--- SIMULAÇÃO DE VENDAS ---\n");

// Registre 5 vendas (array de [idProduto, quantidade])
const vendas = [
  [1, 2], // 2 Notebooks
  [2, 5], // 5 Mouses
  [3, 3], // 3 Teclados
  [1, 1], // 1 Notebook
  [4, 2], // 2 Monitores
];

let totalVendido = 0;

for (let i = 0; i < vendas.length; i++) {
  const idProduto = vendas[i][0];
  const qtdVendida = vendas[i][1];

  // Encontrar produto no estoque
  for (let j = 0; j < estoque.length; j++) {
    if (estoque[j][0] === idProduto) {
      const nomeProduto = estoque[j][1];
      const precoProduto = estoque[j][2];
      const qtdEstoque = estoque[j][3];

      if (qtdEstoque >= qtdVendida) {
        // Realizar venda
        estoque[j][3] -= qtdVendida;
        const valorVenda = precoProduto * qtdVendida;
        totalVendido += valorVenda;

        console.log(
          `✓ Venda ${
            i + 1
          }: ${qtdVendida}x ${nomeProduto} = R$ ${valorVenda.toFixed(2)}`
        );
        console.log(`  Estoque atualizado: ${estoque[j][3]} unidades\n`);
      } else {
        console.log(`✗ Venda ${i + 1}: Estoque insuficiente de ${nomeProduto}`);
        console.log(
          `  Solicitado: ${qtdVendida} | Disponível: ${qtdEstoque}\n`
        );
      }
      break;
    }
  }
}

console.log(`TOTAL VENDIDO: R$ ${totalVendido.toFixed(2)}\n`);

// ===== PARTE 5: PRODUTOS MAIS E MENOS VENDIDOS =====
console.log("--- RANKING DE VENDAS ---\n");

// Criar array de vendas por produto [id, quantidadeVendida]
const rankingVendas = [];

for (let i = 0; i < estoque.length; i++) {
  const idProduto = estoque[i][0];
  let qtdVendida = 0;

  // Contar vendas deste produto
  for (let j = 0; j < vendas.length; j++) {
    if (vendas[j][0] === idProduto) {
      qtdVendida += vendas[j][1];
    }
  }

  if (qtdVendida > 0) {
    rankingVendas.push([estoque[i][1], qtdVendida]);
  }
}

// Ordenar por quantidade vendida (decrescente)
for (let i = 0; i < rankingVendas.length - 1; i++) {
  for (let j = 0; j < rankingVendas.length - i - 1; j++) {
    if (rankingVendas[j][1] < rankingVendas[j + 1][1]) {
      // Trocar posições
      const temp = rankingVendas[j];
      rankingVendas[j] = rankingVendas[j + 1];
      rankingVendas[j + 1] = temp;
    }
  }
}

// Exibir ranking
for (let i = 0; i < rankingVendas.length; i++) {
  console.log(
    `${i + 1}º lugar: ${rankingVendas[i][0]} (${rankingVendas[i][1]} unidades)`
  );
}

// ===== PARTE 6: ESTOQUE APÓS VENDAS =====
console.log("\n--- ESTOQUE APÓS VENDAS ---\n");
console.log("ID\tPRODUTO\t\tQTD ANTERIOR\tQTD ATUAL\tSTATUS");
console.log("-------------------------------------------------------------");

// Implemente a comparação do estoque antes e depois das vendas
// Você precisará salvar o estoque original antes das vendas

console.log("\n========================================");
console.log("   FIM DO RELATÓRIO");
console.log("========================================");
```

**Critérios de avaliação:**

- [ ] Exibe relatório completo do estoque
- [ ] Identifica produtos com estoque baixo
- [ ] Encontra produto mais caro e mais barato
- [ ] Simula vendas e atualiza estoque
- [ ] Valida se há estoque suficiente
- [ ] Calcula total vendido
- [ ] Cria ranking de produtos mais vendidos
- [ ] Usa loops para iterar arrays
- [ ] Usa arrays bidimensionais corretamente
- [ ] Código organizado e comentado
- [ ] Saída formatada e legível

**Desafios extras:**

- Adicione função para cadastrar novos produtos
- Implemente busca de produto por nome
- Crie relatório de lucro (considere preço de custo)
- Adicione categorias de produtos
- Implemente sistema de descontos por quantidade

---

## Parte 8: Checklist de Aprendizado

Ao final da Semana 5, você deve ser capaz de:

- [ ] Criar arrays de diferentes formas
- [ ] Acessar elementos por índice
- [ ] Modificar elementos do array
- [ ] Usar a propriedade length
- [ ] Iterar sobre arrays com loops
- [ ] Adicionar elementos (push, unshift)
- [ ] Remover elementos (pop, shift)
- [ ] Buscar elementos (indexOf, includes)
- [ ] Copiar partes de arrays (slice)
- [ ] Modificar arrays (splice)
- [ ] Ordenar arrays (sort)
- [ ] Inverter arrays (reverse)
- [ ] Converter array em string (join)
- [ ] Trabalhar com arrays bidimensionais
- [ ] Resolver problemas usando arrays

---

## Parte 9: Troubleshooting

### Problema 1: Índice fora dos limites

```javascript
const frutas = ["maçã", "banana", "laranja"];

console.log(frutas[5]); // undefined (não existe)

// ✅ Sempre verifique o tamanho
if (indice >= 0 && indice < frutas.length) {
  console.log(frutas[indice]);
}
```

### Problema 2: Modificar array durante iteração

```javascript
// ❌ PROBLEMA - Array muda durante o loop
const numeros = [1, 2, 3, 4, 5];

for (let i = 0; i < numeros.length; i++) {
  numeros.pop(); // Remove elementos enquanto itera
}
// Comportamento imprevisível!

// ✅ SOLUÇÃO - Itere de trás para frente ou copie
const nums = [1, 2, 3, 4, 5];
for (let i = nums.length - 1; i >= 0; i--) {
  nums.pop();
}
```

### Problema 3: Confundir length com último índice

```javascript
const arr = [10, 20, 30, 40, 50];

// ❌ ERRADO - length é 5, mas último índice é 4
console.log(arr[arr.length]); // undefined

// ✅ CORRETO - último índice é length - 1
console.log(arr[arr.length - 1]); // 50
```

### Problema 4: Arrays como referência

```javascript
// Arrays são passados por referência!
const original = [1, 2, 3];
const copia = original; // ❌ Não é uma cópia real!

copia[0] = 999;
console.log(original); // [999, 2, 3] - original mudou!

// ✅ Para copiar de verdade:
const copiaReal = original.slice();
// ou
const copiaReal2 = [...original]; // (spread operator - ES6)
```

---

## Parte 10: Boas Práticas

### ✅ FAÇA:

1. **Use const para arrays que não serão reatribuídos**

```javascript
const frutas = ["maçã", "banana"];
frutas.push("laranja"); // ✅ Pode modificar conteúdo
// frutas = [];  // ❌ Não pode reatribuir
```

2. **Nomes descritivos no plural**

```javascript
const alunos = ["Ana", "Bruno"]; // ✅
const numeros = [1, 2, 3]; // ✅
const a = ["item1", "item2"]; // ❌
```

3. **Verifique se é array**

```javascript
if (Array.isArray(minhaVariavel)) {
  // código
}
```

4. **Use métodos apropriados**

```javascript
// ✅ Use includes para verificar existência
if (arr.includes(valor)) {
}

// ❌ Não use indexOf só para verificar
if (arr.indexOf(valor) !== -1) {
} // Funciona, mas includes é mais claro
```

### ❌ EVITE:

1. **Arrays com tipos misturados (sem necessidade)**

```javascript
const dados = [1, "texto", true, null]; // ❌ Confuso
```

2. **Modificar length diretamente**

```javascript
arr.length = 0; // ❌ Evite, use métodos adequados
```

3. **Loops com side-effects inesperados**

```javascript
for (let i = 0; i < arr.length; i++) {
  arr.push(i); // ❌ Loop infinito!
}
```

---

## Recursos Adicionais

### Documentação:

- **MDN - Arrays**: https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array
- **JavaScript.info - Arrays**: https://javascript.info/array

### Visualizadores:

- **Array Visualizer**: array-visualizer.com
- **Python Tutor**: pythontutor.com/javascript.html

---

## Preparação para Semana 6

Na próxima semana você aprenderá:

- ✨ Objetos (estruturas chave-valor)
- ✨ Propriedades e métodos
- ✨ Arrays de objetos
- ✨ Manipulação avançada de dados

**Pré-requisito:** Domine arrays, pois usaremos muito com objetos!

---

**Professor:** Marcelo Damasceno de Melo

**Curso:** Introdução ao JavaScript

**Semana:** 5 de 8

**Próxima aula:** Objetos

---
