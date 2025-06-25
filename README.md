# PWM LED Brightness Control – PIC16F877A

This project implements LED brightness control using **PWM** on the **PIC16F877A**. The LED brightness gradually increases and decreases by adjusting the duty cycle of the CCP1 module.

## 👨‍💻 Author
**Edvin Jose Vakaparamban**  
📅 Created on: [Your Date]

---

## 🔧 Overview

- Uses CCP1 module in **PWM mode**.
- Varies duty cycle from 0% to ~85% and back.
- Smooth LED brightness fade-in and fade-out effect.
- Operates on a 16 MHz crystal.

---

## 🧰 Hardware Requirements

- PIC16F877A Microcontroller
- LED with resistor connected to CCP1 output (RC2)
- 16 MHz crystal oscillator
- MPLAB X IDE with XC8 compiler

---

## ⚙️ Configuration

| Parameter         | Value      |
|------------------|------------|
| PWM Output       | RC2 (CCP1) |
| Frequency        | ~1 kHz     |
| Duty Cycle Range | 0 to 350   |
| Timer2 Prescaler | 1:4        |

---

## 💡 Working

1. Timer2 and CCP1 are configured for PWM mode.
2. The duty cycle starts at 0 and increases gradually.
3. LED brightness increases accordingly.
4. After reaching max duty, it decreases.
5. The cycle repeats for continuous fading.

---

## 🧠 Key Code Snippet

```c
while (DC < 350) {
  PWM1_Set_Duty(DC);
  DC++;
  __delay_ms(2);
}
