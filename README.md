# Customer Discovery — CoverExperiences

Base de conocimientos de conversaciones WhatsApp con clientes y hospitality partners de CoverExperiences.

## Estructura

```
/chats
  El-copeo-de-tu-vida-ITA-PALENCIA.txt
  GRUPO-PELICANO.txt
  Kenko.txt
  La-Cabane-Marbella.txt
  Marina-Resort-Benidorm.txt
  Mogli-The-Key.txt
  Nightlife-Madrid.txt
  O-Beach-Ibiza.txt
  Recoletos-Jazz.txt
  Sublim-Beach.txt
```

Cada `.txt` es un export directo de WhatsApp (sin modificar) nombrado por el venue/cliente.

## Cómo actualizar un chat

1. Re-exportar la conversación desde WhatsApp ("Exportar chat" → "Sin archivos multimedia")
2. Reemplazar el `.txt` correspondiente en `/chats`
3. Commit + push
4. En el Claude Project, eliminar el archivo antiguo y subir el nuevo desde GitHub

## Cómo añadir un chat nuevo

1. Exportar desde WhatsApp → guardar como `nombre-venue-ciudad.txt`
2. Añadir a `/chats`
3. Commit + push
4. Subir al Claude Project

**Límite práctico:** mantener ≤12 archivos en el proyecto (por encima, Claude activa RAG por file count y la calidad de citas baja). Si necesitas más de 12, consolida chats pequeños en un solo archivo.

## Convenciones de nombrado

- Minúsculas, guiones, sin espacios: `ocean-club-marbella.txt`
- Si un cliente tiene múltiples chats (ej: uno con CS, otro con Sales), usar sufijo: `ocean-club-marbella-cs.txt`, `ocean-club-marbella-sales.txt`

## Uso con Claude

Este repo alimenta un Claude Project ("Customer Discovery — CoverExperiences") con instrucciones de Customer Discovery Agent que:
- Clasifica insights como Pain / Gain / JTBD / Feature Request / Churn Signal
- Cita textualmente con fecha y speaker
- Conecta cada hallazgo con Segmentos (A/B/C/D) y Pilares 2026

Las instrucciones del proyecto están en `PROJECT_INSTRUCTIONS.md` (para referencia, no se suben al repo de chats).