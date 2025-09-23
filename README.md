# Taller 1 — Simuproc

## Integrantes
- Benjamin Cuello: IO y harness de pruebas
- Bastian Salinas : Biblioteca ALU 16 bits
- Tomas Guerra: Calculadora basica
- Matias Gutierrez: RPN y suma en memoria

## Requisitos
- Simuproc 
- Como correr: abrir Simuproc y cargar el .asm correspondiente

## Mapa de memoria y contratos
- IN = 28h
- A_LO=20h, A_HI=21h, B_LO=22h, B_HI=23h
- R_LO=24h, R_HI=25h
- CARRY=26h
- Temp: 50h–5Fh
- Stack RPN: desde 60h
- Datos ejercicio 3: desde 30h
- Resultado ejercicio 3: 40h (low), 41h (high)

### IO
- `INPUT X`: lee entero y lo guarda en X
- `OUTPUT X`: muestra entero en X
- `OUTPUT_PAIR LO,HI`: muestra primero LO y luego HI

### ALU (B)
- `ADD16(A,B -> R,CARRY)`
- `SUB16(A,B -> R)`
- `MUL16(A,B -> R_LO,R_HI)`
- `DIV16(A,B -> QUOT=R_LO, REM=R_HI)`

## Ejecutar ejemplos
- Calculadora basica: cargar `simuproc/calc_basica/main.asm` y seguir prompts
- RPN: cargar `simuproc/calc_rpn/main.asm`
- Suma memoria: cargar `simuproc/mem_sum/main.asm`

## Pruebas rapidas
- 2,1,3 => 5
- 6,4,2 => 3 y resto 0
- 7,4,3 => 2 y resto 1
- Producto con parte alta != 0
