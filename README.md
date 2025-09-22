# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm

CODE SEGMENT
ASSUME CS: CODE,DS:CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1: MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| AX → 1234H              | [1200H] = 2468H          |
| BX → 1234H              | [1202H] = 00H            |
| CL → 00H                |                          |


#### Manual Calculations

AX = 1234H  
BX = 1234H  
AX + BX = 2468H (no carry)  
CL = 00H  
[1200H] = 2468H, [1202H] = 00H


---

## OUTPUT IMAGE FROM MASM SOFTWARE
<img width="633" height="299" alt="Screenshot 2025-09-21 230237" src="https://github.com/user-attachments/assets/6b8648d2-41fe-44ac-a4db-3be7334dfceb" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE,DS:CODE
ORG 1000H
MOV AX,1234H
MOV BX,1234H
SUB AX,BX
JNC Down
INC CL
Down : MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
| AX → 1234H              | [1200H] = 0000H          |
| BX → 1234H              | [1202H] = 00H            |
| CL → 00H (initial)      |                          |


#### Manual Calculations

AX = 1234H  
BX = 1234H  
AX − BX = 0000H (no borrow)  
CL = 00H  
[1200H] = 0000H, [1202H] = 00H

---


## OUTPUT SCREEN FROM MASM SOFTWARE


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE,DS:CODE
ORG 1000H
MOV DX,0000H
MOV AX,1234H
MOV BX,1234H
MUL BX
MOV SI,1200H
MOV [SI],AX
MOV [SI+02H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|   1200                  |      90 5A 4B 01         |
|   1210                  |      2B 86 76 FF         |
|   1220                  |      BE 72 FF 77         |

#### Manual Calculations

AX = 1234H  
BX = 1234H  
AX × BX = 1234H × 1234H  
        = 14B5A90H  

Result → DX:AX = 014B5A90H  
AX = 5A90H  
DX = 014BH  

Stored:  
[1200H] = AX = 5A90H  
[1202H] = DX = 014BH


---

## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="635" height="434" alt="Screenshot 2025-08-29 084830" src="https://github.com/user-attachments/assets/315c0b8e-c83f-48ea-9d66-8342a9618450" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE,DS:CODE
ORG 1000H
MOV DX,0000H
MOV AX,1234H
MOV BX,1234H
DIV BX
MOV SI,1200H
MOV [SI],AX
MOV [SI+02H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END

```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|      1200               |        01 00 00 00       |

#### Manual Calculations

1234 / 1234  (Q-1 R-0)

---
## OUTPUT FROM MASM SOFTWARE

<img width="633" height="434" alt="Screenshot 2025-08-29 085428" src="https://github.com/user-attachments/assets/5c88c225-aada-4d51-9281-22829a89f444" />




## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.


