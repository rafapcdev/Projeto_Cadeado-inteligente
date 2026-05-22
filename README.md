# 🔒 Projeto Cadeado Inteligente (Smart Lock)

**Chave eletrônica com Arduino Uno**  
*Turma do Curso de Robótica e Automação - Módulo Intermediário – Ciclo 2026.1*

---

## 📖 Sobre o Projeto

O **Cadeado Inteligente** é um projeto de controle de acesso desenvolvido como desafio em sala de aula (proposto pelo professor Rafael Pereira Costa). O sistema utiliza um **Arduino Uno** para controlar uma fechadura eletrônica por meio de uma senha digitada em um teclado matricial.

O projeto foi aplicado na prática na construção de uma caixa (cofre) em miniatura impressa em 3D, que pode ser aberta ou trancada com segurança.

### 🎯 Objetivos
- Controlar o acesso a um recinto ou caixa de forma segura.
- Integrar hardware e software na plataforma Arduino (C/C++).
- Utilizar feedback visual (Display LCD e LEDs) e sonoro (Buzzer) para interação com o usuário.

---

## 🛠️ Componentes e Materiais

| Componente | Detalhes |
| :--- | :--- |
| **Microcontrolador** | Arduino Uno R3 (SMD CH340) |
| **Atuador (Fechadura)** | Servomotor MG90S (180 graus) |
| **Interface de Entrada** | Teclado Matricial de membrana (4x4, 16 teclas) |
| **Interface Visual** | Display LCD 16x2 com módulo I2C |
| **Alimentação** | 2 Baterias 3,7V (Modelo 16340) + Conversor DC-DC Step-Down (LM2596) |
| **Sinalização** | 2 LEDs (Verde e Vermelho), Buzzer Ativo |
| **Outros Componentes** | Protoboard, Resistores (22Ω), Capacitor (10µF), Diodo (1N4007), Jumpers e Mini Chave Gangorra |
| **Estrutura** | Caixa em miniatura feita em Impressora 3D |

*(Custo total estimado do projeto: ~ R$ 217,00)*

---

## ⚙️ Como Funciona

1. **Estado Inicial (Trancado)**: O servomotor fica posicionado em 180°, mantendo a tranca fechada. O display exibe a mensagem "FECHADO".
2. **Inserção da Senha**: O usuário digita a senha de 4 dígitos no teclado matricial. Para cada número digitado, um caractere `*` aparece no display e um pequeno bip é emitido. A tecla `#` pode ser usada para limpar a senha digitada em caso de erro.
3. **Verificação**:
   - **Senha Correta (Padrão: "1111")**: O sistema exibe "Senha Correta!" no display, o LED Verde acende, um aviso sonoro é emitido e o servomotor gira para 90° (abrindo a fechadura). Após 10 segundos, o sistema automaticamente volta à posição trancada (180°).
   - **Senha Incorreta**: O display exibe "Senha Incorreta", o LED Vermelho acende e o buzzer emite 3 bips curtos de alerta de erro. Em seguida, o sistema volta ao estado trancado.

---

## 💻 Código (Arduino C++)

A lógica do sistema foi desenvolvida utilizando a IDE do Arduino, dependendo das seguintes bibliotecas:
- `Keypad.h` (leitura do teclado matricial)
- `Servo.h` (controle de ângulo do servomotor)
- `LiquidCrystal_I2C.h` (controle do display LCD via barramento I2C)

---

## 👥 Equipe do Projeto

- André Alves dos Santos
- Clara Peçanha Neves Motta Amorim da Silva
- Claudio Soares da Rocha
- Davi Marcos Gonçalves de Oliveira
- Deborah dos Santos Nogueira
- Marco Antônio Vasconcelos Filho
- Mário Fernando Margutti Pinto
- Yris Beatriz Goulart Werneck
