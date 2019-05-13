datos
================

[![CRAN
status](https://www.r-pkg.org/badges/version/datos)](https://cran.r-project.org/package=datos)
[![Travis-CI Build
Status](https://travis-ci.org/cienciadedatos/datos.svg?branch=master)](https://travis-ci.org/cienciadedatos/datos)
[![Coverage
status](https://codecov.io/gh/cienciadedatos/datos/branch/master/graph/badge.svg)](https://codecov.io/github/cienciadedatos/datos?branch=master)

Este paquete provee la traducción de datos al español. Los datos
originales provienes de diferentes paquetes de R. Estos son los datos
utilizados para los ejercicios de el libro “R para la Ciencia de Datos”
(R for Data Science). Este paquete se puede utilizar junto con el libro,
o independientemente.

## Instalación

El paquete está disponible en GitHub, y puede ser instalando utilizando
`remotes`:

    remotes::install_github()("cienciadedatos/datos")

## Requisitos

El paquete se concentra en traducir los datos en el momento que los
necesita. **El paquete que contiene los datos en ingles tiene que ya
estar instalado**.

Estos son los paquetes necesarios:

| Paquetes     |
| :----------- |
| nycflights13 |
| Lahman       |
| ggplot2      |
| datasets     |
| gapminder    |
| forcats      |
| tidyr        |

## Traducciones

Las traducciones disponibles dentro de `datos` son las
siguientes:

| Nombre        | Título                                                                                   |
| :------------ | :--------------------------------------------------------------------------------------- |
| aerolineas    | Nombres de aerolíneas                                                                    |
| aeropuertos   | Datos de aeropuertos                                                                     |
| aviones       | Datos de aviones                                                                         |
| bateadores    | Tabla de bateadores                                                                      |
| clima         | Datos de clima                                                                           |
| datos-stringr | Vectores de caracteres dentro del paquete stringr                                        |
| diamantes     | Precio de 50.000 diamantes                                                               |
| encuesta      | Muestra de variables categóricas de una encuesta social                                  |
| fiel          | Datos del geiser Viejo Fiel (Old Faithful)                                               |
| millas        | Datos de economía de combustible de 1999 y 2008 para 38 modelos populares de automóviles |
| mtautos       | Pruebas de ruta de automóviles de Motor Trend                                            |
| oms           | Datos de tuberculosis de la Organización Mundial de la Salud                             |
| paises        | Datos de Gapminder                                                                       |
| presidencial  | Periodos de 11 presidentes, desde Eisenhower a Obama                                     |
| tabla1        | Registros de tuberculosis de la Organización Mundial de la Salud (1era variante)         |
| tabla2        | Registros de tuberculosis de la Organización Mundial de la Salud (2da variante)          |
| tabla3        | Registros de tuberculosis de la Organización Mundial de la Salud (3era variante)         |
| tabla4a       | Registros de tuberculosis de la Organización Mundial de la Salud (3era variante)         |
| tabla4b       | Registros de tuberculosis de la Organización Mundial de la Salud (3era variante)         |
| tabla5        | Registros de tuberculosis de la Organización Mundial de la Salud (3era variante)         |
| vuelos        | Datos de vuelos                                                                          |

## Uso

La libreria `datos` tiene que ser cargada en su sesión de R.

``` r
library(datos)
library(ggplot2)
library(dplyr)
```

Las variables que contienen los datos van a estar disponible para su uso
inmediatemante. Pero, los datos no se van a traducir hasta que la
variable sea “llamada” dentro de código que escribas. En este ejemplo,
los datos `diamonds`, proveniente de `ggplot2`, se cargan en la memoria
R cuando la utilizamos por primera vez.

``` r
glimpse(diamantes)
```

    ## Observations: 53,940
    ## Variables: 10
    ## $ precio      <int> 326, 326, 327, 334, 335, 336, 336, 337, 337, 338, 33…
    ## $ quilate     <dbl> 0.23, 0.21, 0.23, 0.29, 0.31, 0.24, 0.24, 0.26, 0.22…
    ## $ corte       <ord> Ideal, Premium, Bueno, Premium, Bueno, Muy bueno, Mu…
    ## $ color       <ord> E, E, E, I, J, J, I, H, E, H, J, J, F, J, E, E, I, J…
    ## $ claridad    <ord> SI2, SI1, VS1, VS2, SI2, VVS2, VVS1, SI1, VS2, VS1, …
    ## $ profundidad <dbl> 61.5, 59.8, 56.9, 62.4, 63.3, 62.8, 62.3, 61.9, 65.1…
    ## $ tabla       <dbl> 55, 61, 65, 58, 58, 57, 57, 55, 61, 61, 55, 56, 61, …
    ## $ x           <dbl> 3.95, 3.89, 4.05, 4.20, 4.34, 3.94, 3.95, 4.07, 3.87…
    ## $ y           <dbl> 3.98, 3.84, 4.07, 4.23, 4.35, 3.96, 3.98, 4.11, 3.78…
    ## $ z           <dbl> 2.43, 2.31, 2.31, 2.63, 2.75, 2.48, 2.47, 2.53, 2.49…

La variable `diamantes` se puede utilizar como cualquier data set en R

``` r
diamantes %>%
  filter(corte == "Bueno") %>%
  ggplot() +
  geom_boxplot(aes(claridad, precio, fill = claridad)) +
  theme(legend.position = "none") +
  labs(title = "Diamantes", subtitle = "Precio y claridad")
```

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->
