# 🃏 Hermandad del Dashiki — Ultimate Texas (16-bit)

Un juego completo de **Ultimate Texas Hold'em** contra el dealer, con estética pixel-art de 16 bits (paleta tipo SNES), en un solo archivo HTML sin dependencias.

![estética 16-bit](https://img.shields.io/badge/estilo-16--bit-ffcd75) ![sin dependencias](https://img.shields.io/badge/dependencias-0-5ad97a)

## 🎮 Jugar

Abre `index.html` en cualquier navegador moderno. No requiere servidor ni instalación.

O sírvelo localmente:

```bash
python3 -m http.server 8123
# luego abre http://localhost:8123
```

## ✨ Características

- **Reglas reales de Ultimate Texas Hold'em**: Ante + Blind, las 3 decisiones de Play (**3× o 4×** pre-flop, 2× flop, 1× river, o fold) y apuesta lateral **Trips independiente** (la fijas aparte, paga desde trío gane o pierda la mano).
- **Evaluador de manos** propio (mejor de 5 entre 7 cartas) con desempates correctos.
- **Tablas de pago correctas**: el Ante hace *push* si el dealer no liga; el Blind paga según tu mano (1:1 escalera → 500:1 escalera real).
- **Coach por Valor Esperado (EV)**: en cada decisión calcula el EV real de apostar vs. esperar/retirarse y recomienda la de mayor EV — exacto en el river (enumera las 990 manos del dealer), Monte Carlo en pre-flop/flop. La sugerencia siempre concuerda con las probabilidades mostradas.
- **Tope de apuesta inteligente**: nunca te deja apostar un Ante que luego no puedas respaldar con el Play máximo (4×) en los tres momentos.
- **Fichas simuladas**: toca o arrastra fichas de $5/$25/$100/$500 al Ante; stepper aparte para el Trips.
- **Estadísticas de sesión**: manos jugadas, neto acumulado y **% de adherencia al coach**, con reinicio.
- **Persistencia**: el bankroll y las estadísticas se guardan en `localStorage` entre sesiones.
- **Sonidos 8-bit** (Web Audio) en cada acción, con botón para silenciar 🔊/🔇.
- **Animaciones**: reparto y volteo de las cartas del dealer al mostrar.
- **Responsivo**: jugable en escritorio y móvil (iPhone).

## 🛠️ Stack

HTML + CSS + JavaScript vanilla. Cero dependencias, cero build. Todo el arte (cartas, dashiki, fichas) está dibujado con CSS/SVG.

## 📜 Tablas de pago

| Blind paga | | Trips (✦ opcional) | |
|---|---|---|---|
| Escalera real | 500:1 | Escalera real | 50:1 |
| Escalera de color | 50:1 | Escalera de color | 40:1 |
| Póker | 10:1 | Póker | 30:1 |
| Full | 3:1 | Full | 8:1 |
| Color | 3:2 | Color | 7:1 |
| Escalera | 1:1 | Escalera | 4:1 |
| Trío o menos | push | Trío | 3:1 |

Ante y Play pagan 1:1.

## ⚠️ Aviso

Proyecto educativo/recreativo. No es por dinero real ni constituye asesoría de juego.
