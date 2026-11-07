# entregable-1-cicd-jmc-sm

## Integrantes: Jose Manuel Carvajal | Santiago Mesa

## Usuarios git: Jcarvajal0810 | RickJakeS


## a. ¿Qué eventos configuraste para disparar tu workflow y por qué?

-Los eventos configurados fueron el push, el pull request y el workflow_dispatch en la rama main. Cuando hay un commit nuevo se utiliza el push para que lo ejecute; y ya el workflow_dispatch es para ejecutar probar el workflow que esta dentro del action, teniendo en cuenta que segun lo que entendimos, esta ejecucion manual se para es sobre el ultimo commit.

## b. ¿Qué sistema operativo utiliza el runner ubuntu-latest y por qué puede ejecutar tu workflow aunque tu computadora sea Windows o macOS? ¿Qué relación tiene el runner con el shell de los pasos run?

Linux 7.0.0-1019-azure; entonces en el manifiesto en la parte de los jobs en runs-on se especifica que se corra en ubuntu; estos jobs no se ejecutan en las maquinas locales si no que se ejecutan en la nube, mas precisamente en github actions; El runner es el entorno de ejecucion y ese shell de los pasos run se ejecuta dentro de ese entorno de ejecucion, por lo cual para linux se usa es bash en este caso.

## c. Menciona al menos 3 acciones pre-construidas del Marketplace de GitHub Actions no mencionadas en este material. Excluye actions/checkout, actions/setup-python, actions/upload-artifact y aws-actions/configure-aws-credentials, aunque alguna solo aparezca como ejemplo conceptual. Describe qué hacen y para qué sirven.

1. PR-AGENT: Agente open source que revisa el codigo de cada PR, por lo que ayuda a que la comunidad pueda tener un codigo mas limpio en sus proyectos y mayor calidad de entrega y valor.

2. Claude Code Action Official: Revisa PRs, el codigo, repsonde preguntas acerca de ello, hace un rastreo, automatiza tareas y es muy simple porque funciona a traves de prompts.

3. Build and push Docker images: Se usa para construir y mandar imagenes docker a traves de buildx con todas las tareas que sean necesarias.

## d. ¿Qué es un secreto en GitHub Actions y para qué se usa? ¿Cómo lo usarías en tu workflow?

Valores sensibles que configuramos o guardamos fuera del codigo y se usan para no exponer informacion sensible. Se usaria precisamente para por ejemplo guardar credenciales de nube, etc.

## e. Reflexiona sobre el uso de GitHub Actions en tu flujo de trabajo diario. ¿Qué tareas automatizarías? ¿Por qué?

-Jose Manuel Carvajal: Mas que todo tareas de auditoria que no involucren valga la redundancia tareas muy criticas, automatizacion de procesos dentro de la organizacion, poder digitalizar procesos que sean manuales dentro de una organizacion, y uso de la IA para tareas no criticas, en terminos de programacion la de claude me parece interesante pero teniendo en cuenta que siempre alguien debe auditar lo que vaya a hacer esta herramienta.

-Santiago Mesa: Profe, no conocía GitHub Actions y me llamó la atención lo sencillo que resulta automatizar tareas del ciclo de vida del software. En mi trabajo, que se centra en integraciones de un sistema de nómina con sistemas contables, automatizaría la ejecución de pruebas en cada pull request para que ningún cambio llegue a la rama de producción sin validarse. También validaría automáticamente la estructura de los archivos planos que generan las integraciones, pues hoy muchos errores de formato se descubren cuando el cliente intenta cargarlos. Finalmente, usaría análisis estático y reportes de cobertura como apoyo al code review, sin reemplazar la revisión humana, para que el equipo se concentre en la lógica de negocio. En conjunto, esto haría al equipo más eficiente y reduciría los errores que hoy detectamos tarde y que más afectan a los clientes.

