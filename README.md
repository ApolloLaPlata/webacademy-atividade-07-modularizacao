# Atividade 7 — Modularização: Funções e Procedimentos

**Curso:** Web Academy UFAC  
**Disciplina:** Algoritmos e Lógica de Programação  
**Aluno:** Vinicius Miranda de Farias

## Questão 1 — Horas, minutos e segundos para segundos

A função recebe horas, minutos e segundos e retorna o total em segundos: `h * 3600 + m * 60 + s`. Exemplo: 2 h, 15 min e 30 s retornam 8.130 s.

```
programa {
    funcao inteiro totalSegundos(inteiro horas, inteiro minutos, inteiro segundos) {
        inteiro total = horas * 3600 + minutos * 60 + segundos
        retorne total
    }
    funcao inicio() {
        inteiro h, m, s
        escreva("Horas: ")
        leia(h)
        escreva("Minutos: ")
        leia(m)
        escreva("Segundos: ")
        leia(s)
        escreva("Total em segundos: ", totalSegundos(h, m, s))
    }
}
```

## Questão 2 — Polegadas para centímetros

Sabendo que 1 polegada = 2,54 cm, a função recebe o valor em polegadas e retorna o equivalente em centímetros.

```
programa {
    funcao real polegadasParaCentimetros(real polegadas) {
        real centimetros = polegadas * 2.54
        retorne centimetros
    }
    funcao inicio() {
        real polegadas
        escreva("Valor em polegadas: ")
        leia(polegadas)
        escreva("Equivalente em centimetros: ", polegadasParaCentimetros(polegadas))
    }
}
```

## Questão 3 — Os dois primos mais próximos de 1.000

Como uma função retorna apenas um valor, criamos a função `primo` (retorno lógico) e um procedimento que preenche um vetor de duas posições com o primo anterior e o primo posterior a 1.000. O resultado é **997 e 1009**.

```
programa {
    funcao logico primo(inteiro n) {
        se (n < 2) {
            retorne falso
        }
        para (inteiro i = 2; i * i <= n; i++) {
            se (n % i == 0) {
                retorne falso
            }
        }
        retorne verdadeiro
    }
    funcao primosProximosMil(inteiro v[]) {
        inteiro anterior = 999, posterior = 1001
        enquanto (primo(anterior) == falso) {
            anterior = anterior - 1
        }
        enquanto (primo(posterior) == falso) {
            posterior = posterior + 1
        }
        v[0] = anterior
        v[1] = posterior
    }
    funcao inicio() {
        inteiro primos[2]
        primosProximosMil(primos)
        escreva("Primos mais proximos de 1000: ", primos[0], " e ", primos[1])
    }
}
```

## Questão 4 — Número inteiro menor que 50 em números romanos

A função retorna uma cadeia com o equivalente romano (por exemplo, 7 retorna `VII`). Se o número estiver fora da faixa (menor que 1 ou maior/igual a 50), retorna uma mensagem de aviso.

```
programa {
    funcao cadeia paraRomano(inteiro n) {
        se (n < 1 || n >= 50) {
            retorne "Numero fora da faixa: informe de 1 a 49"
        }
        cadeia dezenas[5]
        dezenas[0] = ""
        dezenas[1] = "X"
        dezenas[2] = "XX"
        dezenas[3] = "XXX"
        dezenas[4] = "XL"
        cadeia unidades[10]
        unidades[0] = ""
        unidades[1] = "I"
        unidades[2] = "II"
        unidades[3] = "III"
        unidades[4] = "IV"
        unidades[5] = "V"
        unidades[6] = "VI"
        unidades[7] = "VII"
        unidades[8] = "VIII"
        unidades[9] = "IX"
        cadeia romano = dezenas[n / 10] + unidades[n % 10]
        retorne romano
    }
    funcao inicio() {
        inteiro numero
        escreva("Numero (menor que 50): ")
        leia(numero)
        escreva(paraRomano(numero))
    }
}
```
