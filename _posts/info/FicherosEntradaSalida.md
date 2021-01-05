# Datos para el modelo
Los datos para este modelo se encuentran en el fichero [*Datos*](../dat/Datos.xlsx) de la carpeta [*dat*](../dat). <br>
En dicho fichero están tanto los precios del mercado diario (hoja "Precio") como todas las características técnicas de los grupos generadores (hoja "BDTer").

El fichero [*JuanitoJaimitoJorgitoEXCELaCSV*](JuanitoJaimitoJorgitoEXCELaCSV.py) lee los datos del fichero [*Datos*](../dat/Datos.xlsx) y genera ficheros CSV con los sets (carpeta [*set*](../set)) y parámetros (carpeta [*par*](../par)).

Independientemente del origen de los datos y como se realice su transformación, es importante tener en cuenta que los datos se cargan al modelo con el objeto Dataportal de pyomo. El objeto **Dataportal necesita que se le pasen los datos de una manera determinada. En este ejemplo se ha elegido usar ficheros CSV**, otras alternativas se pueden encontrar en la [documentación de pyomo](https://pyomo.readthedocs.io/en/stable/working_abstractmodels/data/dataportals.html#data-portals).


*  Carpeta [*set*](../set):

    Cada set o set dinámico está en un archivo separado. los nombres de dichos archivos son *nombreset.csv* para sets estáticos y *nombreset(setdependiente1,setdependiente2).csv* para los sets dinámicos.


*  Carpeta [*par*](par):

    Debido a que muchos parámetros comparten los sets de los que dependen, en esta carpeta hay archivos con varios parámetros dentro, organizados por su naturaleza. Por ejemplo, los 11 parámetros técnicos de los grupos que dependen solo del set "gts" se agrupan en el archivo *DGT(gts).csv* mientras que el precio está solo en el archivo *p_Precio(k).csv*.

Ejemplo ficheros **CSV para Sets**:

| Set estático                | Set estático <br> (no se usa en este modelo)  | Set dinámico de 2 dim. <br> (no se usa en este modelo)|          
| :------                     | :------                                       | :------                                               |
| gts.csv                     | arr.csv                                       | paisgts(pais,gts).csv                                 |          
| gts <br> g1 <br> g2 <br> g3 | arr <br> arr1 <br> arr2                       | pais,gts <br> esp,g1 <br> esp,g2 <br> port,g3         |

Ejemplo ficheros **CSV para Parámetros**:

| Parámetro de 2 dim.<br> (no se usa en este modelo)                                                           | Varios parámetros de 1 dim.                                           |
| :------                                                                                                      | :------                                                               |
| p_GTScarr(gts,arr).csv                                                                                       | DGT(gts).csv                                                          |
| gts,arr,p_GTScarr <br> g1,arr1,4 <br> g1,arr2,5 <br> g2,arr1,6 <br> g2,arr2,8 <br> g3,arr1,9 <br> g3,arr2,10 | gts,p_GTSpmn,p_GTSpmx <br> g1,100,200 <br> g2,110,210 <br> g3,120,220 |

# Resultados del modelo
Con la ejecución del modelo (archivo [*JuanitoJaimitoJorgito*](JuanitoJaimitoJorgito.py)), se guardan los valores de las variables en ficheros CSV individuales en la carpeta [*out*](../out). Los nombres de dichos ficheros son *nombrevariable(set1,set2).csv*. <br>
Tras dicha ejecución se puede usar el archivo [*JuanitoJaimitoJorgitoCSVaEXCEL*](JuanitoJaimitoJorgitoCSVaEXCEL.py) para pasar los resultados de esos ficheros CSV al fichero *Resultados.xlsx* (también generado en la carpeta [*out*](../out)).
