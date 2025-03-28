# Respostas do Exercício
# Respostas e Explicações

## 1. Questão 1

### **Resposta:**

**A) O código avalia a expressão booleana, imprime true, calcula o produto dos números na lista e imprime o resultado no console.**

### **Explicação:**

O código é dividido em duas partes. A primeira parte contém uma expressão booleana:

```javascript
//Parte 1
let p = 10;
let q = 3;
let r = 6;

// Expressão booleana que avalia diferentes condições

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado); // Saída: true
```

#### **Por que a resposta é verdadeira?**
- `p % q === 1` → `10 % 3 = 1`, que é verdadeiro.
- `r * 2 > p` → `6 * 2 = 12`, e `12 > 10`, então verdadeiro.
- `(p % q === 1) && (r * 2 > p)` → Ambos são verdadeiros, então o resultado final da primeira parte da expressão é `true`.

A segunda parte calcula o produto dos números em uma lista:

```javascript
const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto); // Saída: O produto dos valores é: 29160
```

---

## 2. Questão 2

### **Resposta:**

**A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'**

### **Explicação:**

As duas funções processam um array de compras para verificar o saldo disponível. A diferença entre elas está na estrutura de repetição:

#### **Função 1 - `do while`**
```javascript
// Comece somando o valor do item atual ao total de compras
// Continue enquanto o total de compras for menor ou igual ao limite
// E enquanto ainda houver itens na lista
do {
    totalCompras += compras[i]; // Adiciona o valor do item atual ao total
    i++; // Passa para o próximo item
} while (limite >= totalCompras && i < compras.length);
```

#### **Função 2 - `while`**
```javascript
// Enquanto o total de compras for menor ou igual ao limite
// E ainda houver itens na lista
while (limite >= totalCompras && i < compras.length) {
    totalCompras += compras[i]; // Adiciona o valor do item atual ao total
    i++; // Passa para o próximo item
}
```

Ambas as funções percorrem o array de compras e somam os valores até atingir o limite. Como os valores das compras e o limite são os mesmos, ambas chegarão à mesma conclusão: **saldo disponível de 400.**

---

## 3. Questão 3

### **Resposta:**

**B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".**

### **Explicação:**

O código segue essa lógica em uma estrutura condicional `if-else`:

```javascript
// Verifica se a idade está entre 18 e 59 anos (inclusive)
if (idade >= 18 && idade < 60) {
    console.log("Você é um adulto!"); // Exibe mensagem para adultos
} 
// Verifica se a idade é menor que 18
else if (idade < 18) {
    console.log("Você é menor de idade!"); // Exibe mensagem para menores de idade
} 
// Caso contrário, a idade é 60 ou mais
else {
    console.log("Você está na melhor idade!"); // Exibe mensagem para pessoas na melhor idade
}
```

O fluxo de execução garante que apenas uma das mensagens será exibida porque a estrutura condicional if-else avalia as condições de forma sequencial e exclusiva. Assim que uma condição é verdadeira, o bloco correspondente é executado, e as demais condições são ignoradas.

---

## 4. Questão 4

### **Resposta:**

**D) Dispositivo 1 ligado. Energia restante: 900**

**Dispositivo 2 ligado. Energia restante: 300**

**Dispositivo 3 ligado com bateria extra. Energia restante: 200**

**Dispositivo 4 não pode ser ligado. Energia insuficiente.**

**Dispositivo 5 não pode ser ligado. Energia insuficiente.**

### **Explicação:**

O código gerencia a energia disponível para ligar dispositivos eletrônicos:

```javascript
// Define a energia inicial disponível e a bateria extra
var energiaDisponivel = 1200;
var bateriaExtra = 400;

// Define o consumo de energia de cada dispositivo
var consumoDispositivos = [300, 600, 500, 200, 400];

// Itera sobre cada dispositivo para verificar se pode ser ligado
for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i]; // Consumo do dispositivo atual

    // Verifica se o dispositivo pode ser ligado com a energia disponível
    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i + 1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo; // Reduz a energia disponível pelo consumo do dispositivo
    } 
    // Verifica se o dispositivo pode ser ligado usando a energia disponível e a bateria extra
    else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i + 1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        bateriaExtra -= (consumo - energiaDisponivel); // Reduz a bateria extra pelo consumo excedente
        energiaDisponivel = 0; // Zera a energia disponível, pois foi totalmente consumida
    } 
    // Caso não haja energia suficiente, o dispositivo não pode ser ligado
    else {
        console.log("Dispositivo " + (i + 1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Cada dispositivo consome energia e, quando necessário, usa a bateria extra. Se não houver energia suficiente, o dispositivo não será ligado.

---

## 5. Questão 5

### **Resposta:**

**B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.**

### **Explicação:**

O método `update()` no Phaser é utilizado para atualizações contínuas no jogo. Por exemplo, movimentação do jogador:

```javascript
update() {
    if (this.cursors.left.isDown) {
        player.setVelocityX(-160);
    } else if (this.cursors.right.isDown) {
        player.setVelocityX(160);
    }
}
```

Isso permite que o jogo reaja instantaneamente às entradas do usuário.

---

## 6. Questão 6

### **Resposta:**

**A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.**

### **Explicação:**

O **Matter.js** permite simular interações físicas realistas:

```javascript
this.matter.add.image(400, 300, 'caixa');
```

Ele suporta colisões avançadas e simulações complexas.


---

## 7.

```javascript
// Array com os valores dos produtos a serem comprados
var compras = [40.50, 20.50, 10.25, 30.85, 65.90];

// Calcula o valor total das compras somando todos os itens do array
var totalCompras = compras.reduce((total, valor) => total + valor, 0);

// Exibe o valor total da compra formatado com duas casas decimais
console.log(`O preço total de suas compras é R$ ${totalCompras.toFixed(2)}`);

// Avalia a categoria do frete com base no valor total da compra
if (totalCompras < 50) {
    console.log("Frete não disponível!"); // Para compras abaixo de R$50,00
} else if (totalCompras <= 199.99) {
    console.log("Frete com custo adicional!"); // Para compras entre R$50,00 e R$199,99
} else {
    console.log("Frete grátis!"); // Para compras de R$200,00 ou mais
}

//Output: O preço total de suas compras é R$ 168.00. Frete com custo adicional!
```

---

## 8.

```javascript
// Classe base Veiculo, que serve como modelo para todos os tipos de veículos
class Veiculo {
    // Construtor que inicializa os atributos do veículo: modelo, ano, quilometragem e litros abastecidos
    constructor(modelo, ano, quilometragem, litrosAbastecidos) {
        this.modelo = modelo;
        this.ano = ano;
        this.quilometragem = quilometragem;
        this.litrosAbastecidos = litrosAbastecidos;
    }

    // Método genérico para calcular o consumo de combustível (km por litro)
    // O cálculo é feito dividindo a quilometragem pelos litros abastecidos
    calcularConsumo() {
        return this.quilometragem / this.litrosAbastecidos;
    }
}

// Classe Carro que herda da classe Veiculo
class Carro extends Veiculo {
    // Construtor específico para a classe Carro, além dos atributos herdados de Veiculo,
    // adiciona atributos específicos como número de passageiros e tipo de combustível
    constructor(modelo, ano, numPassageiros, combustivel, quilometragem, litrosAbastecidos) {
        super(modelo, ano, quilometragem, litrosAbastecidos); // Chama o construtor da classe base (Veiculo)
        this.numPassageiros = numPassageiros; // Número de passageiros do carro
        this.combustivel = combustivel; // Tipo de combustível do carro (ex: gasolina, álcool, etc.)
    }

    // O cálculo do consumo é herdado da classe Veiculo, então não há necessidade de sobrescrever aqui
}

// Classe Moto que herda da classe Veiculo
class Moto extends Veiculo {
    // Construtor específico para a classe Moto, que além dos atributos herdados,
    // adiciona atributos próprios, como o tipo de guidão e tipo de exaustão
    constructor(modelo, ano, guidao, exaustao, quilometragem, litrosAbastecidos) {
        super(modelo, ano, quilometragem, litrosAbastecidos); // Chama o construtor da classe base (Veiculo)
        this.guidao = guidao; // Tipo de guidão (ex: esportivo, custom)
        this.exaustao = exaustao; // Tipo de exaustão (ex: simples, esportiva)
    }

    // O cálculo do consumo também é herdado da classe Veiculo, logo não precisa ser sobrescrito aqui
}

// Exemplo de uso das classes:
let carro1 = new Carro("Sedan X", 2022, 5, "Gasolina", 500, 50);
// Exibe o consumo de combustível do carro, que é calculado pela quilometragem e litros abastecidos
console.log(`Consumo do carro: ${carro1.calcularConsumo()} km/L`);

let moto1 = new Moto("Sport 300", 2023, "Esportivo", "Esportiva", 300, 15);
// Exibe o consumo de combustível da moto, que também é calculado da mesma forma
console.log(`Consumo da moto: ${moto1.calcularConsumo()} km/L`);
```

---

## 9.

```pseudo
// Variáveis
velocidadeInicial    = valor
velocidade_pouso     = valor
tempo_max            = valor
desaceleracao        = valor
limite_desaceleracao = valor

tempo = 0
velocidade = velocidadeInicial

// Loop que atualiza a velocidade enquanto a velocidade for maior que a velocidade segura e o tempo não exceder o tempo máximo
enquanto velocidade > velocidade_pouso && tempo <= tempo_max {
    velocidade = velocidadeInicial - desaceleracao * tempo
    tempo += 1;

    // Verificar se a desaceleração não ultrapassa seu limite estabelecido
    se desaceleracao < limite_desaceleracao {
        print 'Ajuste a taxa de desaceleração, pois ela está baixa'
    }
}

// Verificar se a sonda conseguiu chegar na velocidade segura dentro do tempo
se velocidade <= velocidade_pouso {
    print `Foi um pouso bem-sucedido. Foi feito em ${tempo} segundos`
}

// Verificar se o tempo máximo foi excedido e a velocidade segura não foi atingida
se tempo > tempo_max {
    print "O tempo máximo foi ultrapassado e a sonda não pousou com segurança"
}
```

---

## 10.

```javascript
function multiplicarMatrizesInvestimento(matrizA, matrizB) {
    // Verifica se o número de colunas de matrizA é igual ao número de linhas de matrizB
    if (matrizA[0].length !== matrizB.length) {
        return "As matrizes não podem ser multiplicadas. O número de colunas de matrizA não é igual ao número de linhas de matrizB.";
    }

    var matrizResultado = [];

    // Loop para percorrer as linhas de matrizA
    for (let i = 0; i < matrizA.length; i++) {
        matrizResultado[i] = [];
        
        // Loop para percorrer as colunas de matrizB
        for (let j = 0; j < matrizB[0].length; j++) {
            matrizResultado[i][j] = 0;

            // Loop para calcular o produto escalar das linhas de matrizA com as colunas de matrizB
            for (let k = 0; k < matrizA[0].length; k++) {
                matrizResultado[i][j] += matrizA[i][k] * matrizB[k][j];
            }
        }
    }
    return matrizResultado;
}
```
