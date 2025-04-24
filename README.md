<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Login</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #0056b3;
            --primary-dark: #004494;
            --secondary-color: #f8f9fa;
            --accent-color: #28a745;
            --accent-dark: #218838;
            --danger-color: #dc3545;
            --danger-dark: #c82333;
            --warning-color: #ffc107;
            --warning-dark: #e0a800;
            --info-color: #17a2b8;
            --info-dark: #138496;
            --text-color: #343a40;
            --border-color: #dee2e6;
            --light-gray: #f5f5f5;
            --gray: #6c757d;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light-gray);
            color: var(--text-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 28px;
        }
        
        .logo h1 {
            font-size: 24px;
            font-weight: 600;
        }
        
        .login-container {
            max-width: 400px;
            margin: 80px auto;
        }
        
        .card {
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            margin-bottom: 20px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .card-header {
            background-color: var(--secondary-color);
            padding: 15px 20px;
            border-bottom: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .card-title {
            font-size: 18px;
            font-weight: 600;
            margin: 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card-body {
            padding: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
            color: var(--text-color);
        }
        
        .form-control {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            font-size: 14px;
            transition: border-color 0.3s, box-shadow 0.3s;
        }
        
        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 86, 179, 0.1);
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
            padding: 8px 16px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
        }
        
        .btn-success {
            background-color: var(--accent-color);
        }
        
        .btn-success:hover {
            background-color: var(--accent-dark);
        }
        
        .login-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }
        
        .alert {
            padding: 10px 15px;
            border-radius: 4px;
            margin-bottom: 15px;
            display: none;
        }
        
        .alert-danger {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .alert-success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-lock"></i>
                    <h1>Sistema de Acceso</h1>
                </div>
            </div>
        </div>
    </header>
    
    <div class="container">
        <div class="login-container">
            <div class="card">
                <div class="card-header">
                    <h2 class="card-title"><i class="fas fa-user-circle"></i> Iniciar Sesión</h2>
                </div>
                <div class="card-body">
                    <div id="alert-message" class="alert"></div>
                    
                    <form id="login-form">
                        <div class="form-group">
                            <label for="username"><i class="fas fa-user"></i> Usuario</label>
                            <input type="text" id="username" class="form-control" placeholder="Ingrese su usuario" required>
                        </div>
                        <div class="form-group">
                            <label for="password"><i class="fas fa-key"></i> Contraseña</label>
                            <input type="password" id="password" class="form-control" placeholder="Ingrese su contraseña" required>
                        </div>
                        
                        <div class="login-buttons">
                            <button type="button" id="user-login" class="btn">
                                <i class="fas fa-sign-in-alt"></i> Acceso Usuario
                            </button>
                            <button type="button" id="admin-login" class="btn btn-success">
                                <i class="fas fa-user-shield"></i> Acceso Admin
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const userLoginBtn = document.getElementById('user-login');
            const adminLoginBtn = document.getElementById('admin-login');
            const usernameInput = document.getElementById('username');
            const passwordInput = document.getElementById('password');
            const alertMessage = document.getElementById('alert-message');
            
            // Función para mostrar mensajes
            function showMessage(message, type) {
                alertMessage.textContent = message;
                alertMessage.className = 'alert ' + type;
                alertMessage.style.display = 'block';
                
                // Ocultar mensaje después de 3 segundos
                setTimeout(() => {
                    alertMessage.style.display = 'none';
                }, 3000);
            }
            
            // Login para usuarios regulares
            userLoginBtn.addEventListener('click', function() {
                const username = usernameInput.value.trim();
                const password = passwordInput.value.trim();
                
                if (username === '' || password === '') {
                    showMessage('Por favor complete todos los campos', 'alert-danger');
                    return;
                }
                
                // Para usuario normal, cualquier usuario y contraseña son válidos
                showMessage('¡Acceso exitoso como usuario regular!', 'alert-success');
                
                // Redirigir a página de Mundialito
                setTimeout(() => {
                    window.location.href = 'mundialito.html';
                }, 1500);
            });
            
            // Login para administradores
            adminLoginBtn.addEventListener('click', function() {
                const username = usernameInput.value.trim();
                const password = passwordInput.value.trim();
                
                if (username === '' || password === '') {
                    showMessage('Por favor complete todos los campos', 'alert-danger');
                    return;
                }
                
                // Verificar credenciales de administrador
                if (username === 'admin' && password === 'admin123') {
                    showMessage('¡Acceso exitoso como administrador!', 'alert-success');
                    
                    // Redirigir a página de Mundialito
                    setTimeout(() => {
                        window.location.href = 'mundialito.html';
                    }, 1500);
                } else {
                    showMessage('Credenciales de administrador incorrectas', 'alert-danger');
                }
            });
        });
    </script>
</body>
</html>
