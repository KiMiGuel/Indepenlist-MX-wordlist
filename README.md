# 🇲🇽 Indepenlist-MX-wordlist

> *Contraseña* — hmmm... alguien que está en contra de señas. 🧐

En toda la red no hay ni una wordlist en español. Aquí va una compilación de palabras mexicanas reales. Que le sean de utilidad.

[📥 Descargar Release v2.0.0](https://github.com/KiMiGuel/Indepenlist-MX-wordlist/releases/tag/v2.0.0)
---

## 📦 Las 2 listas

| Archivo | Líneas | Tamaño | Para qué usarla |
|---|---|---|---|
| `mx_passwords.txt` | ~9.6M | 115 MB | 🔑 Wordlist general de contraseñas — nombres, cultura mexicana, mutaciones y leetspeak. |
| `mx_router.txt` | ~1.5M | 22 MB | 📡 Candidatos específicos para router/WiFi — patrones ISP (MAC/SSID), gibberish válido WPA y control aleatorio real. |

> 💡 **Pro tip:** Contraseñas generales → `mx_passwords.txt`. Auditoría de router/red WiFi → `mx_router.txt`, más dirigida.

---

## 🛠️ ¿Cómo se hicieron?

1. 🧹 **Limpieza** — UTF-8 forzoso, acentos corregidos, fantasmas eliminados (BOM, zero-width, mojibake).
2. 🔗 **Fusión** — Consolidadas en 2 categorías: contraseñas generales (`passwords`) y candidatos router/WiFi (`router`).
3. 📊 **Deduplicación real** — Overlap verificado línea por línea antes de fusionar, no supuesto.
4. ✂️ **Curación** — Contenido mecánico/redundante confirmado por overlap real se descarta.

> 🎯 El 61% de las contraseñas mexicanas miden entre 8 y 13 caracteres, y la gran mayoría son **palabra + números**.

---

## 🚀 Cómo usar

### Hashcat
```bash
hashcat -m 22000 handshake.hccapx mx_passwords.txt
```

### Aircrack-ng
```bash
aircrack-ng handshake.cap -w mx_router.txt
```

### John the Ripper
```bash
john --wordlist=mx_passwords.txt hash.txt
```

### Hydra
```bash
hydra -l usuario -P mx_passwords.txt target ssh
```

> ⚡ Ataques generales → `mx_passwords.txt`. Routers/WiFi → `mx_router.txt`. Combina con reglas (`-r` en Hashcat) para más cobertura.

---

## 📁 Contenido del release

```
├── mx_passwords.txt   ← 🔑 contraseñas generales
└── mx_router.txt      ← 📡 candidatos router/WiFi
```

---

## ⚖️ Disclaimer

Estas listas son el resultado de limpiar, deduplicar y fusionar datos públicos aplicando patrones lingüísticos del español mexicano. **Úsalas solo en entornos autorizados.**

---

*Hecho con 🌮 y paciencia en México.*

**Pórtense bien, cabrones.**
