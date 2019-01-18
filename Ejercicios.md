1. Tienes que modificar la escena 5 de Hamlet en el fichero scene-5.txt. En dicha escena Hamlet encuentra al fantasma de su padre. Añade este texto al fichero:
> Ghost: 
> My hour is almost come,
> When I to sulphurous and tormenting flames
> Must render up myself.
2. Añade scene-5.txt al área de preparación.
3. Haz un commit con los cambios con un buen mensaje de commit.
4. Modifica las palabras del fantasma. Aquí tienes una sugerencia divertida:
> Ghost: 
> My hour is almost come,
> When I to sulphurous and tormenting balloons
> Must render up myself.
5. Devuelve el fichero al estado del último commit.
6. Cambia el nombre de LARRY por LAERTES en los ficheros scene-3.txt y scene-7.txt.
7. Añade los ficheros al área de preparación usando un único comando git.
8. Vamos a cometer un error a propósito. Borra cualquier línea del fichero scene-2.txt.
9. Añade scene-2.txt al área de preparación.
10. Comprueba el estado del repositorio. 
11. Devuelve scene-2.txt al directorio de trabajo.
12. Haz un commit para guardar los cambios realizados en el nombre de Larry por Laertes.
13. Busca el primer commit que has hecho y vuelve a dicho commit. Indica como has buscado el commit anterior y como has vuelto a él.
14. Crea una nueva rama llamada **reinventando_hamlet**
15. Cámbiate a dicha rama
16. Mejora la escena 2 como creas conveniente.
17. Haz un commit con los cambios con un mensaje adecuado.
18. Vuelve a la rama master.
19. Elimina la rama **reinventando_halet**
20. Crea una nueva rama, modifica algo en la rama master, haz commit y llévate los cambios a la rama que has creado.
21. Provoca un conflicto entre la rama master y la rama que has creado (indica lo que has hecho). Une la rama a la rama master resolviendo el conflicto.

RESPUESTAS

**Robert Filip**

1. Primero he clonado el repositorio para tenerlo localmente:
 git clone https://github.com/IESJacaranda/deshaciendo-cambios-y-gestion-de-ramas-Kirissuno.git 
Y después para añadir el texto al fichero he usado:
echo "Ghost: My hour is almost come, When I to sulphurous and tormenting flames Must render up myself." >> scene-5.txt 

2. **git add scene-5.txt**

3. **git commit -m "Este es un buen mensaje de commit"**

4. Para ello lo que he hecho es usar nano y editar la palabra que se cambió: flames a balloons.

5. **git checkout 02fd051 scene-5.txt**
Donde 02fd051 es el checkout anterior averiguado mediante el comando **git log --oneline**

6. Simplemente he usado nano para editar cada fichero y cambiar los Larry por Laertes aunque podríamos haber usado el comando sed.

7. **git add ***

8. He editato el fichero scene-2.txt y borrado la segunda frase de dicho fichero.

9. **git add scene-2.txt**

10. **git status**
Donde podremos ver que tenemos 3 ficheros en modificados esperando para ser subidos al repositorio o revertidos.

11. **git reset HEAD scene-2.txt**

12. **git commit -m "Cambiado nombre de Larry por Laertes"**

13. Lo primero que he hecho es usar:
**git log --oneline **
Y averiguar cual es mi primer commit, ahora para volver a dicho commit he usado:
**git checkout 02fd051 .**

14. **git branch reinventando_hamlet** 

15. **git checkout reinventando_hamlet**

16. **echo "Hamlet dies" >> scene-2.txt**

17. **git commit -am "Hamlet muere"**

18. **git checkout master**

19. Al intentar hacer:
**git branch -d reinventando_hamlet**
Da error porque no está a la par con el master y está adelantado por ello me pide que si estoy de acuerdo con ello usar:
**git branch -D reinventando_hamlet**

20. **git branch nuevarama**
He añadido un nuevo fichero llamado scene-1.txt y hecho commit:
**touch scene-1.txt
git add scene-1.txt
git commit -m "Añadido scene1"**
Y ahora me he movido a la nueva rama en la cual he ejecutado el siguiente comando para hacerle el merge con el master:
**git checkout nuevarama
git merge master**

21. Para crear el conflicto he editado en las 2 ramas el fichero scene-2.txt en la cual he editado un número, después he hecho commit en las 2 ramas y por último estando en la rama master he usado el comando:
**git merge nuevarama**
Con la cual me da error. Para ver el error he usado:
**git diff nuevarama**
Y me sale la línea diferente la cual edito en la rama master para que quede igual que en la nuevarama y le hago commit, ahora al hacer merge ya no tiene error.
