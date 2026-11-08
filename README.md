# entregable-1-cicd-jmc-sm

## Integrantes: Jose Manuel Carvajal | Santiago Mesa

## Usuarios git: Jcarvajal0810 | RickJakeS


## a. ¿Qué eventos configuraste para disparar tu workflow y por qué?

Los eventos configurados fueron el push, el pull request y el workflow_dispatch en la rama main. Cuando hay un commit nuevo, se utiliza el push para que lo ejecute; y ya el workflow_dispatch es para ejecutar y probar de forma manual el workflow que está dentro de action, teniendo en cuenta que, según lo que entendimos, cada vez que se dispara un evento de forma manual, este se ejecuta sobre el último commit.

## b. ¿Qué sistema operativo utiliza el runner ubuntu-latest y por qué puede ejecutar tu workflow aunque tu computadora sea Windows o macOS? ¿Qué relación tiene el runner con el shell de los pasos run?

Linux 7.0.0-1019-azure; entonces, en el manifiesto, en la parte de los jobs en runs-on se especifica que se corra en ubuntu; estos jobs no se ejecutan en las máquinas locales, sino que se ejecutan en la nube, más precisamente en github actions; El runner es el entorno de ejecución y ese shell de los pasos run se ejecuta dentro de ese entorno de ejecución, por lo cual para Linux se usa bash en este caso.

## c. Menciona al menos 3 acciones pre-construidas del Marketplace de GitHub Actions no mencionadas en este material. Excluye actions/checkout, actions/setup-python, actions/upload-artifact y aws-actions/configure-aws-credentials, aunque alguna solo aparezca como ejemplo conceptual. Describe qué hacen y para qué sirven.

1. PR-AGENT: Agente open source que revisa el código de cada PR, por lo que ayuda a que la comunidad pueda tener un código más limpio en sus proyectos y mayor calidad de entrega y valor.

2. Claude Code Action Official: Revisa PRs, el código, responde preguntas acerca de ello, hace un rastreo, automatiza tareas y es muy simple porque funciona a través de prompts.

3. Build and push Docker images: Se usa para construir y mandar imágenes Docker a través de buildx con todas las tareas que sean necesarias.

## d. ¿Qué es un secreto en GitHub Actions y para qué se usa? ¿Cómo lo usarías en tu workflow?

Valores sensibles que configuramos o guardamos fuera del código y se usan para no exponer información sensible. Se usaría precisamente para guardar credenciales de nube, entre otra información sensible.

## e. Reflexiona sobre el uso de GitHub Actions en tu flujo de trabajo diario. ¿Qué tareas automatizarías? ¿Por qué?

-Jose Manuel Carvajal: Más que todo, tareas de auditoría que no involucren, valga la redundancia, tareas muy críticas, automatización de procesos dentro de la organización, poder digitalizar procesos que sean manuales dentro de una organización y uso de la IA para tareas no críticas. En términos de programación, la de Claude me parece interesante, pero teniendo en cuenta que siempre alguien debe auditar lo que vaya a hacer esta herramienta.

-Santiago Mesa: Profe, no conocía GitHub Actions y me llamó la atención lo sencillo que resulta automatizar tareas del ciclo de vida del software. En mi trabajo, que se centra en integraciones de un sistema de nómina con sistemas contables, automatizaría la ejecución de pruebas en cada pull request para que ningún cambio llegue a la rama de producción sin validarse. También validaría automáticamente la estructura de los archivos planos que generan las integraciones, pues hoy muchos errores de formato se descubren cuando el cliente intenta cargarlos. Finalmente, usaría análisis estático y reportes de cobertura como apoyo al code review, sin reemplazar la revisión humana, para que el equipo se concentre en la lógica de negocio. En conjunto, esto haría al equipo más eficiente y reduciría los errores que hoy detectamos tarde y que más afectan a los clientes.

## Ejecución exitosa del workflow

[Ejecución #3 de mi_workflow.yml (commit 9ac492e)](https://github.com/Jcarvajal0810/entregable-1-cicd-jmc-sm/actions/runs/42399409457)