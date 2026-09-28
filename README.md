# Selector de idioma para el perfil de GitHub Saxt35

Este documento define cómo mantener dos versiones del README del perfil
de GitHub y permitir cambiar fácilmente entre inglés y español.

## Estructura de archivos

``` text
Saxt35/
├── README.md       # Versión principal en inglés
├── README.es.md    # Versión en español
├── DESCRIPTION.md
├── CHANGELOG.md
├── assets/
├── docs/
└── templates/
```

## Selector de idioma

Agregar la siguiente línea al inicio de **ambos archivos**, antes del
título principal:

``` md
[🇺🇸 English](README.md) | [🇲🇽 Español](README.es.md)
```

### Inicio de `README.md`

``` md
[🇺🇸 English](README.md) | [🇲🇽 Español](README.es.md)

# Noé Briones Pérez

## AI Architect | Solution Architect
```

### Inicio de `README.es.md`

``` md
[🇺🇸 English](README.md) | [🇲🇽 Español](README.es.md)

# Noé Briones Pérez

## AI Architect | Solution Architect
```

## Regla de mantenimiento

`README.md` será la versión principal del perfil y GitHub la mostrará
automáticamente en la página de `Saxt35`.

`README.es.md` será la traducción al español.

Para evitar diferencias entre ambas versiones:

1.  Realizar primero los cambios de contenido en `README.md`.
2.  Traducir esos mismos cambios a `README.es.md`.
3.  Mantener la misma estructura, secciones, proyectos y significado en
    ambos archivos.
4.  No agregar capacidades, tecnologías o afirmaciones a una versión que
    no estén presentes en la otra.
5.  Mantener los nombres propios de tecnologías, productos, repositorios
    y estándares cuando corresponda.

## Resultado esperado

El visitante podrá cambiar de idioma desde la primera línea del README:

**🇺🇸 English \| 🇲🇽 Español**

La versión inglesa seguirá siendo la página principal del perfil,
mientras que la versión española estará disponible a un clic.
