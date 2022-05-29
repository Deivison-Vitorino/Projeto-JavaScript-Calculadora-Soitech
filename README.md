# Calculadora Java Script

![](https://github.com/Deivison-Vitorino/Projeto-JavaScript-Calculadora-Soitech/blob/main/img/design.PNG)

**Utilizando JavaScript na lógica da calculadora**

```javascript
var numero1 = "";
var numero2 = "";
var operacao = "";


const alterarNumero = (n) => {
    if(operacao !== "") 
        numero2 += n.toString();
        numero2 = parseInt(numero2);
        document.getElementById("digitos").value = numero1 + operacao + numero2;
    } else {
        numero1 += n.toString();
        numero1 = parseInt(numero1);
        document.getElementById('digitos').value = numero1;
    }
};

    
const altertaroperacao = (simmbolo) => {
    operacao = simmbolo;
    document.getElementById("digitos").value = numero1 + operacao;
};


const calcular = () => {
    var resultado = 0
    switch (operacao) {
        case "+":
            resultado = numero1 + numero2;
        break;
        case "-":
            resultado = numero1 - numero2;
        break;
        case "*":
            resultado = numero1 * numero2;
        break;
        case "/":
            resultado = numero1 / numero2;
            break;                        

    }


    numero1 = "";
    numero2 = "";
    operacao = "";

    document.getElementById("digitos").value = resultado;
}

```

**Classes CSS**

```css
body{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}


.btn-operador{
    color: #f19eaa;
    background-color: #909090;
    border-color: #000000;
    border-width: 1px;
    width: 40px;
    height: 40px;
    font-size: 22px;
}


.btn-number{
    color: #ffff;
    background-color: #6bc178;
    border-color: #000000;
    border-width: 1px;
    width: 40px;
    height: 40px;
    font-size: 22px;
}


.btn-igual{
    color: #ffff;
    background-color: #f19eaa;
    border-color: #000000;
    border-width: 1px;
    width: 40px;
    height: 80px;
    font-size: 22px;
}


.calculadora{
    background-color: #909090;
    display: flex;
    flex-direction: column;
    height: 286px;
    width: 166px;
    justify-content: center;
    align-items: center;
}    


.tela{
    width: 160px;
    height: 80px;
    background-color: transparent;
    border: none;
    border-color: #000000;
    border-width: 1px;
    border-style: solid;
    color: white;
    text-align: right;
}


.teclado{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    
}


.btn-linha_baixa{
    display: flex;
    width: 120px;
    flex-wrap: wrap;
}
```

**Página html**

```html
<html>
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" width=device-width, initial-scale=1.0 />
        <title>Document</title>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div class="calculadora">
            <input id="digitos" value="" readonly  class="tela"/> 
            <div class="teclado">
                <button class="btn-operador" onclick="altertaroperacao(C)">C</button>
                <button class="btn-operador" onclick="altertaroperacao('%')">%</button>
                <button class="btn-operador" onclick="altertaroperacao('/')">/</button>
                <button class="btn-operador" onclick="altertaroperacao('*')">x</button>
                <button class="btn-number" onclick="alterarNumero(7)">7</button>
                <button class="btn-number" onclick="alterarNumero(8)">8</button>
                <button class="btn-number" onclick="alterarNumero(9)">9</button>
                <button class="btn-operador" onclick="altertaroperacao('-')">-</button>
                <button class="btn-number" onclick="alterarNumero(4)">4</button>
                <button class="btn-number" onclick="alterarNumero(5)">5</button>
                <button class="btn-number" onclick="alterarNumero(6)">6</button>
                <button class="btn-operador" onclick="altertaroperacao('+')">+</button>
                <div class="btn-linha_baixa">
                    <button class="btn-number" onclick="alterarNumero(1)">1</button>
                    <button class="btn-number" onclick="alterarNumero(2)">2</button>
                    <button class="btn-number" onclick="alterarNumero(3)">3</button>
                    <button class="btn-number" onclick="alterarNumero(0)">0</button>
                    <button class="btn-operador" onclick="altertaroperacao(.)">.</button>
                    <button class="btn-operador" onclick="altertaroperacao()"></button>
                </div>
                <button class="btn-igual" onclick="calcular()">=</button>
            </div>
        </div>
        <script src="scripts.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    </body>
</html>
```
