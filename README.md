# SCLI - Informe Entrega 4 (PFC) - GA-SUM-06 / PE-U5

Documento LaTeX individual de aplicación de la guía de práctica
experimental GA-SUM-06 / PE-U5 --- CI/CD, Pruebas y Observabilidad,
de la asignatura Aplicaciones Distribuidas, sobre el Sistema de Control
de Laboratorios Informáticos (SCLI), desarrollado como Proyecto de Fin
de Curso (ISR-701).

**Autor:** Harold Nicolás Vinueza Sánchez
**Carrera:** Software, Facultad de Ciencias de la Computación, UTEQ
**Sistema evaluado:** SCLI (Sistema de Control de Laboratorios Informáticos)
**Repo de código del proyecto:** https://github.com/ffarinangog2/Entrega-final-del-PFC (rama `feature/entrega-4`)

## Estructura del repo

## Estructura del repo

​```
main.tex              -> documento fuente LaTeX (informe completo)
main.pdf               -> documento compilado (entregable final)
referencias/
  bibliografia.bib     -> referencias en formato BibTeX (estilo IEEE)
fuentes-pdf/
  *.pdf                -> PDFs de las referencias con DOI, subrayados
                           con comentarios indicando en qué sección
                           del informe se utiliza cada fragmento
​```

## Cómo compilar el documento

### Opción 1: automático (recomendado)

Cada vez que se hace `push` a `main` con cambios en `main.tex` o en
`referencias/`, un workflow de GitHub Actions
(`.github/workflows/build-pdf.yml`) compila el documento
automáticamente con `latexmk` y sube el `main.pdf` actualizado al
repositorio mediante un commit automático. No es necesario compilar en
local para mantener el PDF al día; basta con revisar la pestaña
**Actions** del repositorio tras cada push.

### Opción 2: compilar en local

Requiere una distribución de TeX completa (por ejemplo, TeX Live o
MiKTeX) con soporte para `pdflatex` y `bibtex`.

Desde la raíz del repositorio:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Se ejecuta `pdflatex` dos veces después de `bibtex` porque la primera
pasada resuelve las referencias cruzadas (`\ref`, `\cite`) y la
bibliografía, y la segunda pasada actualiza la numeración final y el
índice con esa información ya resuelta. El resultado es `main.pdf` en
la raíz del repositorio.

## Sobre las fuentes en `fuentes-pdf/`

Cada PDF corresponde a una referencia bibliográfica citada en
`main.tex` que cuenta con DOI verificado y acceso abierto. Los PDFs
incluyen subrayado sobre los fragmentos específicos utilizados como
respaldo de afirmaciones del informe, junto con un comentario que
indica la sección del documento en la que se emplea esa evidencia.