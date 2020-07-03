Para ejecutar el codigo localmente primero nosotros, despues de paralelizarlo lo compilamos con gcc y openMP, para ello usamos:

- gcc -openmp omp_mxm_serial.c -lm -o omp_mxm_serial

donde -lm es para las liberias matematicas, compilara un ejecutable omp_mxm_serial que podremos ejecutar en local con :

~$ ./omp_mxm_serial

Para ejecutar el codigo en el guane, compilamos de igual forma que en la anterior aclaracion y luego creamos un archivo sbatch donde configuraremos el numero de nodos, cpus, tareas por nodos y nombres para archivo de entrada y errores y tambien al final el nombre del ejecutable que abrira, esa configuracion se podra observar en el archivo mxm_serial.sbatch en este repositorio.

lo ejecutamos con:

~$ sbatch mxm_serial.sbatch

y el se enlazara con el ./omp_mxm_serial , o el ejecutable establecido al final de las lineas del documento sbatch y generara un .out y un .err, si el .err esta vacio , miramos el .out y alli estara el resultado.
