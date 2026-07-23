El proyecto implementa un sistema básico de autenticación web utilizando Flask, Flask-Login y MySQL. Su funcionamiento se basa en una arquitectura donde el usuario interactúa inicialmente con un formulario HTML. Al enviar sus credenciales, Flask recibe la información mediante la ruta /login y procesa la solicitud.

Posteriormente, el sistema crea un objeto User y lo envía al método ModelUser.login(). Este método realiza una consulta a la base de datos para localizar al usuario mediante su nombre de usuario. Si encuentra un registro, obtiene el hash de la contraseña almacenada y realiza la comprobación correspondiente.

Si las credenciales son válidas, se ejecuta login_user() para establecer la sesión autenticada y el usuario es redirigido a la página principal mediante redirect(url_for('home')). Si el usuario no existe o la contraseña no coincide, se muestra un mensaje de error y se vuelve a presentar el formulario de inicio de sesión.

La base de datos observada contiene los campos id, username, password y fullname, mientras que el campo de contraseña se encuentra almacenado mediante un mecanismo de hash, lo cual es una práctica adecuada frente al almacenamiento de contraseñas en texto plano. El proyecto también cuenta con dependencias específicas para Flask, autenticación, conexión con MySQL y gestión de formularios, como se observa en su archivo de requisitos.

En términos sencillos, el sistema funciona como un portero digital: el usuario presenta su nombre y contraseña, Flask recibe la solicitud, ModelUser consulta la base de datos, se verifica la contraseña y, si todo es correcto, Flask-Login permite el acceso. Si las credenciales no son válidas, el sistema rechaza el acceso.
