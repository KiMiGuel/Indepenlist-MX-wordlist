[LEEME(1).md](https://github.com/user-attachments/files/31088237/LEEME.1.md)

# 🇲🇽 Indepenlist-MX-wordlist

> *Contraseña* — hmmm... alguien que está en contra de señas. 🧐

En toda la red no hay ni una wordlist en español. Aquí va una compilación de palabras mexicanas reales. Que le sean de utilidad. Ahí te va, carnal.

[![Release v1.0.0](https://img.shields.io/badge/Release-v1.0.0-blue)](https://github.com/KiMiGuel/Indepenlist-MX-wordlist/releases/tag/v1.0.0)

---

## 📦 Las 4 listas

| Archivo | Líneas | Tamaño | Para qué usarla |
|---|---|---|---|
| `mexican_wordlist_final.txt` | ~7.7M | 90 MB | 🥇 **Empieza aquí.** Mejor relación tamaño/cobertura. |
| `mexican_wordlist_full.txt` | ~9.0M | 108 MB | 🌎 El arsenal completo. |
| `mexican_wordlist_core.txt` | ~1.9M | 29 MB | 🧠 Ataques dirigidos a humanos (nombres, lugares, frases). |
| `mexican_wordlist_mangled.txt` | ~1.7M | 19 MB | 🤖 Variantes con leetspeak y mutaciones. |

> 💡 **Pro tip:** Si solo vas a bajar una, agarra `mexican_wordlist_final.txt`.

---

## 🛠️ ¿Cómo se hicieron?

1. 🧹 **Limpieza** — UTF-8 forzoso, acentos corregidos, fantasmas eliminados (BOM, zero-width, mojibake).
2. 🔗 **Fusión** — Separadas en tiers: humano (`core`), mutado (`mangled`) y global (`full`).
3. 📊 **PACK** — Análisis de máscaras con `statsgen` para encontrar los patrones más comunes.
4. ✂️ **Optimización** — La lista `final` conserva solo las palabras que coinciden con las máscaras del 80% más frecuente.

> 🎯 El 61% de las contraseñas mexicanas miden entre 8 y 13 caracteres, y la gran mayoría son **palabra + números**.

---

## 🚀 Cómo usar

### Hashcat
```bash
hashcat -m 22000 handshake.hccapx mexican_wordlist_final.txt
```

### Aircrack-ng
```bash
aircrack-ng handshake.cap -w mexican_wordlist_final.txt
```

### John the Ripper
```bash
john --wordlist=mexican_wordlist_final.txt hash.txt
```

### Hydra
```bash
hydra -l usuario -P mexican_wordlist_core.txt target ssh
```

> ⚡ Usa `final` para un primer barrido rápido. Si no rompe, prueba `full` o combina con reglas (`-r` en Hashcat).

---

## 📁 Estructura

```
├── mexican_wordlist_final.txt      ← 🥇 empieza aquí
├── mexican_wordlist_full.txt       ← 🌎 todo
├── mexican_wordlist_core.txt       ← 🧠 humano
├── mexican_wordlist_mangled.txt    ← 🤖 mutado
├── LEEME.md                        ← 📖 estás aquí
├── scripts/                        ← 🐍 scripts de limpieza y fusión
└── pack_out/                       ← 📊 stats y máscaras de PACK
```

---

## ⚖️ Disclaimer

Estas listas son el resultado de limpiar, deduplicar y fusionar datos públicos aplicando patrones lingüísticos del español mexicano. **Úsalas solo en entornos autorizados.** Portense bien cabrones**.

---

*Hecho con 🌮 y paciencia en México.*

**Pórtense bien, cabrones.**
