# Parent App
Proyecto básico de spring-boot web

Contiene una carpeta `commons` dentro del directorio de `k8/config` que es una copia del contenido del repositorio *git-subtree-child-devops* ( https://github.com/javierlopez40/git-subtree-child-devops ).

### Configuración
- Agregar la url del repositorio devops al proyecto con el siguiente comando:

	`git remote add devops <URL>`

- Agregar el repositorio devops como una carpeta dentro del proyecto actual. Utilizando el parámetro `--squash` se copia el contenido del repositorio hijo, sin conservar el histórico de este dentro el repositorio padre.

	`git subtree add --prefix=k8s/config/commons/ devops master --squash`

### Comandos para trabajar con ambos repositorios
- Se debe tener en cuenta que para repositar todas la modificaciones del proyecto atual, seguiremos utilizando los comando *git [pull | fetch | push |...] ...*

- Si realizamos una modificación del contenido del repositorio hijo, y queremos que este quede reflejado en el repositorio *devops* se debe ejecutar lo siguiente:

	`git subtree push --prefix=k8s/config/commons/ devops master`

- Para actualizar el contenido del repositorio *devops* dentro del proyecto actual, ejecutar lo siguiente:

	`git subtree pull --prefix=k8s/config/commons/ devops master --squash`

