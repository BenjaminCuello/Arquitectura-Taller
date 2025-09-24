# Harness de Pruebas – Taller Arquitectura (SimuProc 1.4.3.0)

Estos harness son programas base que preparan las entradas, dejan un espacio para la rutina de cada integrante y muestran los resultados.

---

## Ejercicio 1 – Calculadora básica

; harness ejercicio 1: calculadora basica
; entradas: dato1, operador, dato2
; resultado esperado: OUT (8 bits) o R_LO/R_HI (16 bits)

LDT
STA 20h ; A_LO = primer dato

LDT
STA 26h ; TMP = operador (1 suma, 2 resta, 3 mul, 4 div)

LDT
STA 22h ; B_LO = segundo dato

; mostrar resultados
; si es suma/resta → OUT
LDA 27h
EAP

; si es mul/div → R_LO y R_HI
LDA 24h
EAP
LDA 25h
EAP

HLT

```

---

## Ejercicio 2 – Calculadora RPN


; harness ejercicio 2: calculadora RPN
; entradas: abajo, tope, operador
; resultado esperado: OUT (8 bits) o R_LO/R_HI (16 bits)

LDT
STA 22h     ; B_LO = abajo

LDT
STA 20h     ; A_LO = tope

LDT
STA 26h     ; TMP = operador (1 suma, 2 resta, 3 mul, 4 div)



; mostrar resultados
LDA 27h
EAP

LDA 24h
EAP
LDA 25h
EAP



## Ejercicio 3 – Suma de 4 palabras de 16 bits


; harness ejercicio 3: suma de 4 palabras de 16 bits
; cada palabra ocupa 2 bytes: low, high
; datos en 30h..37h

LDT
STA 30h     ; palabra0 low
LDT
STA 31h     ; palabra0 high

LDT
STA 32h     ; palabra1 low
LDT
STA 33h     ; palabra1 high

LDT
STA 34h     ; palabra2 low
LDT
STA 35h     ; palabra2 high

LDT
STA 36h     ; palabra3 low
LDT
STA 37h     ; palabra3 high



; mostrar resultado final en 40h/41h
LDA 40h
EAP
LDA 41h
EAP

HLT
```
