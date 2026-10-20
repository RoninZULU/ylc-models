# Modelos de Your Last Coach

Archivos que la app [Your Last Coach](https://providencehq.es/yourlastcoach/) descarga una sola vez, cuando quien la usa lo pide. Todo funciona dentro del móvil: ninguna foto sale de él.

## Reconocedor de platos (`food-vision-v1`)

`siglip2_food_v1.tflite` es la parte de imagen de **SigLIP 2** ([google/siglip2-base-patch16-224](https://huggingface.co/google/siglip2-base-patch16-224)), de Google, publicada con licencia **Apache 2.0**.

Cambios respecto al original:
- Reescrita en TensorFlow con los mismos pesos y convertida a TensorFlow Lite. Coincide con el original (similitud del coseno 0,99999994).
- Pesos cuantizados a 8 bits (rango dinámico) para que ocupe 90 MB en vez de 352 MB.
- Entrada: la foto de 224 × 224 en 196 cuadrados de 16 × 16 × 3, con valores de −1 a 1. Salida: un vector de 768, normalizado.

La app compara ese vector con el de cada alimento de su base para proponer qué hay en el plato.

- SHA-256: `6b2c0a23c9dff2610b4aa90339ce25af99aff7210eeb3ee2ddeb1cb74f5ddbe3`
- Tamaño: 94.124.056 bytes

## Licencia

Apache 2.0 (ver `LICENSE`). SigLIP 2 © Google LLC. La conversión y la cuantización son de Providence.
