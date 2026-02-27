<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agenda Scolaire 📚</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .header {
            text-align: center;
            color: white;
            margin-bottom: 40px;
            animation: float 3s ease-in-out infinite;
        }
        
        .header h1 {
            font-size: 3.5em;
            margin-bottom: 10px;
            text-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }
        
        .header p {
            font-size: 1.2em;
            opacity: 0.9;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .auth-container {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            max-width: 500px;
            margin: 0 auto;
            animation: slideUp 0.3s ease;
        }
        
        @keyframes slideUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
        
        .auth-container h2 {
            color: #333;
            margin-bottom: 30px;
            text-align: center;
            font-size: 2em;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            color: #666;
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 0.95em;
        }
        
        .form-group input,
        .form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 1em;
            font-family: 'Poppins', sans-serif;
            transition: all 0.3s;
        }
        
        .form-group input:focus,
        .form-group select:focus {
            outline: none;
            border-color: #667eea;
            background: #f8f9ff;
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }
        
        .avatar-upload-register {
            margin-bottom: 20px;
        }
        
        .avatar-upload-register label {
            display: block;
            color: #666;
            font-weight: 600;
            margin-bottom: 15px;
            font-size: 0.95em;
        }
        
        .avatar-input-label {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 30px;
            border: 2px dashed #667eea;
            border-radius: 15px;
            background: #f8f9ff;
            cursor: pointer;
            transition: all 0.3s;
            gap: 15px;
            text-align: center;
        }
        
        .avatar-input-label:hover {
            background: #f0f2ff;
            border-color: #5568d3;
            transform: translateY(-2px);
        }
        
        .avatar-input-label.has-file {
            background: #e8f5e9;
            border-color: #20c997;
        }
        
        .avatar-preview-register {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            border: 3px solid white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            font-size: 2.5em;
        }
        
        .avatar-preview-register img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .avatar-input-label span {
            font-size: 3em;
            color: #667eea;
        }
        
        .avatar-input-label p {
            font-weight: 600;
            color: #667eea;
            margin: 0;
        }
        
        .button {
            padding: 12px 30px;
            border: none;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            width: 100%;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
        }
        
        .btn-secondary {
            background: #e0e0e0;
            color: #333;
        }
        
        .btn-secondary:hover {
            background: #ccc;
        }
        
        .auth-toggle {
            text-align: center;
            margin-top: 20px;
            color: #666;
        }
        
        .auth-toggle a {
            color: #667eea;
            cursor: pointer;
            font-weight: 600;
            text-decoration: none;
        }
        
        .auth-toggle a:hover {
            text-decoration: underline;
        }
        
        .role-selector {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            margin-bottom: 30px;
            text-align: center;
        }
        
        .role-buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 20px;
        }
        
        @media (max-width: 768px) {
            .role-buttons {
                grid-template-columns: 1fr 1fr;
            }
        }
        
        .role-btn {
            padding: 20px;
            border: 3px solid #e0e0e0;
            background: white;
            border-radius: 15px;
            cursor: pointer;
            font-size: 1.2em;
            font-weight: 700;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .role-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
        }
        
        .role-btn.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: transparent;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }
        
        .user-profile {
            background: white;
            border-radius: 15px;
            padding: 15px 25px;
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .user-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
            font-size: 1.5em;
            overflow: hidden;
            border: 3px solid white;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
        }
        
        .user-avatar:hover {
            transform: scale(1.05);
        }
        
        .user-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .user-avatar-edit {
            position: absolute;
            bottom: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s;
            color: white;
            font-size: 1.2em;
        }
        
        .user-avatar:hover .user-avatar-edit {
            opacity: 1;
        }
        
        .user-info {
            flex: 1;
        }
        
        .user-name {
            font-weight: 700;
            color: #333;
            font-size: 1.1em;
        }
        
        .user-class {
            color: #999;
            font-size: 0.9em;
        }
        
        .logout-btn {
            background: #ff6b6b;
            color: white;
            padding: 8px 16px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .logout-btn:hover {
            background: #ff5252;
            transform: translateY(-2px);
        }
        
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 2000;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .modal-overlay.show {
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 20px;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: slideUp 0.3s ease;
        }
        
        .modal-content h2 {
            color: #333;
            margin-bottom: 20px;
            text-align: center;
            font-size: 1.8em;
        }
        
        .modal-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }
        
        .notification-toast {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.2);
            animation: slideInRight 0.3s ease;
            z-index: 3000;
            display: none;
        }
        
        @keyframes slideInRight {
            from {
                transform: translateX(400px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        .notification-toast.show {
            display: block;
        }
        
        .notification-toast.success {
            border-left: 4px solid #20c997;
            color: #20c997;
            font-weight: 600;
        }
        
        .notification-toast.error {
            border-left: 4px solid #ff6b6b;
            color: #ff6b6b;
            font-weight: 600;
        }
        
        .main-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        @media (max-width: 1024px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
        }
        
        .card {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            border-top: 5px solid #667eea;
        }
        
        .card h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 1.8em;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card select,
        .card textarea,
        .card input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 1em;
            font-family: 'Poppins', sans-serif;
            margin-bottom: 20px;
            transition: all 0.3s;
        }
        
        .card select:focus,
        .card textarea:focus,
        .card input:focus {
            outline: none;
            border-color: #667eea;
            background: #f8f9ff;
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }
        
        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .file-upload-wrapper {
            position: relative;
            display: inline-block;
            width: 100%;
        }
        
        .file-input-label {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            border: 2px dashed #667eea;
            border-radius: 10px;
            background: #f8f9ff;
            cursor: pointer;
            transition: all 0.3s;
            gap: 10px;
            font-weight: 600;
            color: #667eea;
            margin-bottom: 20px;
        }
        
        .file-input-label:hover {
            background: #f0f2ff;
            border-color: #5568d3;
            transform: translateY(-2px);
        }
        
        .file-input-label.has-file {
            background: #e8f5e9;
            border-color: #20c997;
            color: #20c997;
        }
        
        .file-upload-wrapper input[type="file"] {
            display: none;
        }
        
        .events-container {
            max-height: 600px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .events-container::-webkit-scrollbar {
            width: 8px;
        }
        
        .events-container::-webkit-scrollbar-track {
            background: #f1f1f1;
            border-radius: 10px;
        }
        
        .events-container::-webkit-scrollbar-thumb {
            background: #667eea;
            border-radius: 10px;
        }
        
        .event-item {
            background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
            padding: 15px;
            border-left: 4px solid #667eea;
            border-radius: 10px;
            margin-bottom: 15px;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .event-item:hover {
            transform: translateX(5px);
            border-color: #667eea;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.2);
        }
        
        .event-item.homework {
            border-left-color: #ffa502;
        }
        
        .event-item.exam {
            border-left-color: #ff6b6b;
        }
        
        .event-item.project {
            border-left-color: #20c997;
        }
        
        .event-item.test {
            border-left-color: #ee5a6f;
        }
        
        .event-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 10px;
        }
        
        .event-title {
            font-weight: 700;
            color: #333;
            font-size: 1.1em;
        }
        
        .event-type {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8em;
            font-weight: 600;
            text-transform: uppercase;
        }
        
        .event-type.homework {
            background: #fff3e0;
            color: #ffa502;
        }
        
        .event-type.exam {
            background: #ffe0e0;
            color: #ff6b6b;
        }
        
        .event-type.project {
            background: #e0f7e9;
            color: #20c997;
        }
        
        .event-type.test {
            background: #ffe0e8;
            color: #ee5a6f;
        }
        
        .event-time {
            color: #666;
            font-size: 0.9em;
            margin-bottom: 8px;
        }
        
        .event-description {
            color: #555;
            font-size: 0.95em;
            margin-bottom: 10px;
            line-height: 1.4;
        }
        
        .event-subject {
            color: #667eea;
            font-weight: 600;
            font-size: 0.9em;
            margin-bottom: 8px;
        }
        
        .event-professor {
            color: #667eea;
            font-weight: 600;
            font-size: 0.85em;
            margin-top: 5px;
        }
        
        .event-recipient {
            color: #667eea;
            font-weight: 600;
            font-size: 0.85em;
            margin-top: 5px;
        }
        
        .pdf-link {
            display: inline-block;
            margin-top: 10px;
            padding: 8px 15px;
            background: #667eea;
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .pdf-link:hover {
            background: #5568d3;
            transform: translateY(-2px);
        }
        
        .no-events {
            text-align: center;
            color: #999;
            padding: 40px 20px;
            font-size: 1.1em;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin-top: 30px;
        }
        
        @media (max-width: 768px) {
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }
        
        .stat-number {
            font-size: 2.5em;
            font-weight: 700;
            margin-bottom: 10px;
        }
        
        .stat-label {
            font-size: 0.9em;
            opacity: 0.9;
        }
        
        .filters {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        
        .filter-btn {
            padding: 8px 16px;
            border: 2px solid #e0e0e0;
            background: white;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9em;
        }
        
        .filter-btn:hover {
            border-color: #667eea;
            color: #667eea;
        }
        
        .filter-btn.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: transparent;
        }
        
        .search-box {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 1em;
            margin-bottom: 20px;
            transition: all 0.3s;
        }
        
        .search-box:focus {
            outline: none;
            border-color: #667eea;
            background: #f8f9ff;
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }
        
        .today-btn {
            background: #20c997;
            color: white;
            width: 100%;
        }
        
        .today-btn:hover {
            background: #12b886;
        }
        
        .hidden {
            display: none !important;
        }
        
        .btn-full {
            width: 100%;
        }
        
        .calendar {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
            border-radius: 15px;
            color: white;
            margin-bottom: 20px;
        }
        
        .calendar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .calendar-header button {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .calendar-header button:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        .calendar-header h3 {
            font-size: 1.5em;
        }
        
        .days-header {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 5px;
            margin-bottom: 10px;
        }
        
        .day-name {
            text-align: center;
            font-weight: 700;
            padding: 10px 5px;
            font-size: 0.9em;
        }
        
        .days-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 5px;
        }
        
        .day {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
            border: 2px solid transparent;
            position: relative;
        }
        
        .day:hover {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .day.today {
            background: #f093fb;
            border-color: white;
            font-weight: 700;
        }
        
        .day.selected {
            background: white;
            color: #667eea;
            border-color: #667eea;
            font-weight: 700;
        }
        
        .day.other-month {
            opacity: 0.5;
            cursor: default;
        }
        
        .day.has-event::after {
            content: '';
            position: absolute;
            bottom: 3px;
            width: 6px;
            height: 6px;
            background: #f093fb;
            border-radius: 50%;
        }
        
        input[type="file"] {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HEADER -->
        <div class="header">
            <h1>📚 Agenda Scolaire</h1>
            <p>Gère tes devoirs, examens et projets facilement</p>
        </div>
        
        <!-- LOGIN/REGISTER -->
        <div id="authContainer" class="auth-container">
            <h2 id="authTitle">📖 Connexion</h2>
            
            <div id="loginForm">
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" id="loginEmail" placeholder="ton@email.com">
                </div>
                
                <div class="form-group">
                    <label>Mot de passe</label>
                    <input type="password" id="loginPassword" placeholder="••••••••">
                </div>
                
                <button class="button btn-primary" onclick="login()">Se Connecter</button>
                
                <div class="auth-toggle">
                    Pas de compte ? <a onclick="switchToRegister()">Créer un compte</a>
                </div>
            </div>
            
            <div id="registerForm" class="hidden">
                <div class="avatar-upload-register">
                    <label>Photo de profil</label>
                    <label for="registerAvatarFile" class="avatar-input-label" id="avatarLabel">
                        <span>📸</span>
                        <p>Clique pour ajouter une photo</p>
                    </label>
                    <input type="file" id="registerAvatarFile" accept="image/*" onchange="handleAvatarSelect()">
                    <div id="avatarPreviewContainer" style="text-align: center; margin-top: 15px;">
                        <div class="avatar-preview-register">👤</div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Nom</label>
                    <input type="text" id="registerName" placeholder="Jean Dupont">
                </div>
                
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" id="registerEmail" placeholder="ton@email.com">
                </div>
                
                <div class="form-group">
                    <label>Mot de passe</label>
                    <input type="password" id="registerPassword" placeholder="••••••••">
                </div>
                
                <div class="form-group">
                    <label>Confirmer le mot de passe</label>
                    <input type="password" id="registerPassword2" placeholder="••••••••">
                </div>
                
                <div class="form-group">
                    <label>Classe</label>
                    <select id="registerClass">
                        <option value="">Choisir une classe</option>
                        <option value="6ème">6ème</option>
                        <option value="5ème">5ème</option>
                        <option value="CM2">CM2</option>
                        <option value="CM1">CM1</option>
                        <option value="CE2">CE2</option>
                        <option value="CE1">CE1</option>
                    </select>
                </div>
                
                <button class="button btn-primary" onclick="register()">Créer un Compte</button>
                
                <div class="auth-toggle">
                    Déjà inscrit ? <a onclick="switchToLogin()">Se connecter</a>
                </div>
            </div>
        </div>
        
        <!-- MAIN APP (Hidden until login) -->
        <div id="mainApp" class="hidden">
            <!-- USER PROFILE -->
            <div class="user-profile">
                <div class="user-avatar" id="userAvatar" onclick="document.getElementById('profileAvatarFile').click()">
                    <div id="userAvatarContent">👤</div>
                    <div class="user-avatar-edit">✏️</div>
                </div>
                <input type="file" id="profileAvatarFile" accept="image/*" onchange="changeProfileAvatar()">
                <div class="user-info">
                    <div class="user-name" id="userName">Jean Dupont</div>
                    <div class="user-class" id="userClass">Classe: CM2</div>
                </div>
                <button class="logout-btn" onclick="logout()">🔓 Déconnexion</button>
            </div>
            
            <!-- ROLE SELECTOR -->
            <div class="role-selector">
                <h2 style="color: #333; margin-bottom: 20px;">Choisir un Rôle</h2>
                <div class="role-buttons">
                    <button class="role-btn active" onclick="selectRole('eleve')">👨‍🎓 ÉLÈVE</button>
                    <button class="role-btn" onclick="selectRole('professeur')">👨‍🏫 PROFESSEUR</button>
                    <button class="role-btn" onclick="selectRole('bulletin')">📄 BULLETIN</button>
                    <button class="role-btn" onclick="selectRole('notifications')">🔔 NOTIFICATIONS</button>
                </div>
            </div>
            
            <!-- ÉLÈVE VIEW -->
            <div id="eleveView" class="main-grid">
                <!-- LEFT: RECHERCHE & LISTE -->
                <div>
                    <div class="card">
                        <h2>🎓 Mes Tâches</h2>
                        
                        <input type="text" class="search-box" id="searchBox" placeholder="Rechercher un événement..." onkeyup="filterTasksSearch()">
                        
                        <div class="filters">
                            <button class="filter-btn active" onclick="filterTasks('all')">Tous</button>
                            <button class="filter-btn" onclick="filterTasks('homework')">📝 Devoirs</button>
                            <button class="filter-btn" onclick="filterTasks('exam')">📋 Examens</button>
                            <button class="filter-btn" onclick="filterTasks('test')">✏️ Tests</button>
                            <button class="filter-btn" onclick="filterTasks('project')">🎯 Projets</button>
                        </div>
                        
                        <div class="events-container" id="tasksContainer">
                            <div class="no-events">Sélectionne une date</div>
                        </div>
                    </div>
                </div>
                
                <!-- RIGHT: CALENDRIER -->
                <div>
                    <div class="card">
                        <div class="calendar">
                            <div class="calendar-header">
                                <button onclick="previousMonth()">◀ Précédent</button>
                                <h3 id="currentMonth"></h3>
                                <button onclick="nextMonth()">Suivant ▶</button>
                            </div>
                            
                            <div class="days-header">
                                <div class="day-name">Lun</div>
                                <div class="day-name">Mar</div>
                                <div class="day-name">Mer</div>
                                <div class="day-name">Jeu</div>
                                <div class="day-name">Ven</div>
                                <div class="day-name">Sam</div>
                                <div class="day-name">Dim</div>
                            </div>
                            
                            <div class="days-grid" id="daysGrid"></div>
                        </div>
                        
                        <button class="button today-btn btn-full" onclick="goToToday()" style="margin-top: 15px;">📅 Aujourd'hui</button>
                    </div>
                    
                    <!-- STATISTIQUES -->
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-number" id="totalTasks">0</div>
                            <div class="stat-label">Total</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="homeworkCount">0</div>
                            <div class="stat-label">Devoirs</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="examCount">0</div>
                            <div class="stat-label">Examens</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="upcomingCount">0</div>
                            <div class="stat-label">À Venir</div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- PROFESSEUR VIEW -->
            <div id="professeurView" class="hidden main-grid">
                <!-- LEFT: AJOUTER ÉVÉNEMENT + BULLETIN -->
                <div>
                    <!-- AJOUTER ÉVÉNEMENT -->
                    <div class="card">
                        <h2>➕ Ajouter un Événement</h2>
                        
                        <div class="form-group">
                            <label>Titre de l'événement</label>
                            <input type="text" id="eventTitle" placeholder="Ex: Devoir de maths">
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label>Date limite</label>
                                <input type="date" id="eventDate">
                            </div>
                            <div class="form-group">
                                <label>Heure</label>
                                <input type="time" id="eventTime">
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label>Classe</label>
                                <select id="eventClass">
                                    <option value="">Choisir une classe</option>
                                    <option value="6ème">6ème</option>
                                    <option value="5ème">5ème</option>
                                    <option value="CM2">CM2</option>
                                    <option value="CM1">CM1</option>
                                    <option value="CE2">CE2</option>
                                    <option value="CE1">CE1</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label>Matière</label>
                                <select id="eventSubject">
                                    <option value="">Choisir une matière</option>
                                    <option value="Français">Français</option>
                                    <option value="Mathématiques">Mathématiques</option>
                                    <option value="Histoire">Histoire</option>
                                    <option value="Géographie">Géographie</option>
                                    <option value="Sciences">Sciences</option>
                                    <option value="Anglais">Anglais</option>
                                    <option value="Éducation Physique">Éducation Physique</option>
                                    <option value="Arts Plastiques">Arts Plastiques</option>
                                    <option value="Musique">Musique</option>
                                    <option value="Informatique">Informatique</option>
                                    <option value="Philosophie">Philosophie</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>Type d'événement</label>
                            <select id="eventType">
                                <option value="homework">📝 Devoir</option>
                                <option value="exam">📋 Examen</option>
                                <option value="test">✏️ Test</option>
                                <option value="project">🎯 Projet</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label>Description</label>
                            <textarea id="eventDescription" placeholder="Ajoute des détails..." rows="4"></textarea>
                        </div>
                        
                        <button class="button btn-primary btn-full" onclick="addEvent()">Ajouter l'événement</button>
                    </div>
                    
                    <!-- ENVOYER BULLETIN -->
                    <div class="card" style="margin-top: 30px;">
                        <h2>📤 Envoyer un Bulletin</h2>
                        
                        <div class="form-group">
                            <label>Sélectionner un élève</label>
                            <select id="bulletinStudent">
                                <option value="">Choisir un élève...</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label>Fichier PDF</label>
                            <div class="file-upload-wrapper">
                                <label for="bulletinFile" class="file-input-label" id="fileLabel">
                                    <span>📎</span>
                                    <span>Clique pour ajouter un PDF</span>
                                </label>
                                <input type="file" id="bulletinFile" accept=".pdf" onchange="handleFileSelect()">
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>Nom/Description</label>
                            <input type="text" id="bulletinName" placeholder="Ex: Bulletin Trimestre 1">
                        </div>
                        
                        <button class="button btn-primary btn-full" onclick="sendBulletin()">Envoyer le Bulletin</button>
                    </div>
                    
                    <!-- AJOUTER NOTIFICATION -->
                    <div class="card" style="margin-top: 30px;">
                        <h2>📢 Ajouter une Notification</h2>
                        
                        <div class="form-group">
                            <label>Titre de la notification</label>
                            <input type="text" id="notifTitle" placeholder="Ex: Important!">
                        </div>
                        
                        <div class="form-group">
                            <label>Message</label>
                            <textarea id="notifMessage" placeholder="Écris ton message..." rows="4"></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label>Type de notification</label>
                            <select id="notifType">
                                <option value="normal">📢 Normal</option>
                                <option value="important">⚠️ Important</option>
                            </select>
                        </div>
                        
                        <button class="button btn-primary btn-full" onclick="addNotification()">Envoyer la notification</button>
                    </div>
                    
                    <!-- RECHERCHE ET FILTRES -->
                    <div class="card" style="margin-top: 30px;">
                        <h2>📋 Événements Créés</h2>
                        
                        <input type="text" class="search-box" id="searchBoxProf" placeholder="Rechercher un événement..." onkeyup="filterEventsSearch()">
                        
                        <div class="filters">
                            <button class="filter-btn active" onclick="filterEventsProfesseur('all')">Tous</button>
                            <button class="filter-btn" onclick="filterEventsProfesseur('homework')">📝 Devoirs</button>
                            <button class="filter-btn" onclick="filterEventsProfesseur('exam')">📋 Examens</button>
                            <button class="filter-btn" onclick="filterEventsProfesseur('test')">✏️ Tests</button>
                            <button class="filter-btn" onclick="filterEventsProfesseur('project')">🎯 Projets</button>
                        </div>
                        
                        <div class="events-container" id="eventsContainer">
                            <div class="no-events">Aucun événement créé</div>
                        </div>
                    </div>
                </div>
                
                <!-- RIGHT: CALENDRIER -->
                <div>
                    <div class="card">
                        <div class="calendar">
                            <div class="calendar-header">
                                <button onclick="previousMonthProf()">◀ Précédent</button>
                                <h3 id="currentMonthProf"></h3>
                                <button onclick="nextMonthProf()">Suivant ▶</button>
                            </div>
                            
                            <div class="days-header">
                                <div class="day-name">Lun</div>
                                <div class="day-name">Mar</div>
                                <div class="day-name">Mer</div>
                                <div class="day-name">Jeu</div>
                                <div class="day-name">Ven</div>
                                <div class="day-name">Sam</div>
                                <div class="day-name">Dim</div>
                            </div>
                            
                            <div class="days-grid" id="daysGridProf"></div>
                        </div>
                        
                        <button class="button today-btn btn-full" onclick="goToTodayProf()" style="margin-top: 15px;">📅 Aujourd'hui</button>
                    </div>
                    
                    <!-- STATISTIQUES -->
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-number" id="totalEvents">0</div>
                            <div class="stat-label">Total</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="homeworkCountProf">0</div>
                            <div class="stat-label">Devoirs</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="examCountProf">0</div>
                            <div class="stat-label">Examens</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="upcomingCountProf">0</div>
                            <div class="stat-label">À Venir</div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- BULLETIN VIEW -->
            <div id="bulletinView" class="hidden main-grid">
                <!-- LEFT: MES BULLETINS -->
                <div>
                    <div class="card">
                        <h2>📄 Mes Bulletins Scolaires</h2>
                        
                        <div class="events-container" id="bulletinsContainer">
                            <div class="no-events">Aucun bulletin reçu</div>
                        </div>
                    </div>
                </div>
                
                <!-- RIGHT: STATS -->
                <div>
                    <div class="card">
                        <h2>📊 Statistiques</h2>
                        
                        <div class="stats-grid" style="margin-top: 20px;">
                            <div class="stat-card">
                                <div class="stat-number" id="totalBulletins">0</div>
                                <div class="stat-label">Total</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- NOTIFICATIONS VIEW -->
            <div id="notificationsView" class="hidden main-grid">
                <!-- LEFT: VIEW NOTIFICATIONS -->
                <div>
                    <div class="card">
                        <h2>📢 Notifications</h2>
                        
                        <div class="events-container" id="notificationsContainer">
                            <div class="no-events">Aucune notification</div>
                        </div>
                    </div>
                </div>
                
                <!-- RIGHT: NOTIFICATIONS STATS -->
                <div>
                    <div class="card">
                        <h2>📊 Statistiques</h2>
                        
                        <div class="stats-grid" style="margin-top: 20px;">
                            <div class="stat-card">
                                <div class="stat-number" id="totalNotifications">0</div>
                                <div class="stat-label">Total</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number" id="importantNotifications">0</div>
                                <div class="stat-label">Important</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- PASSWORD MODAL -->
    <div class="modal-overlay" id="passwordModal">
        <div class="modal-content">
            <h2>🔐 Accès Professeur</h2>
            
            <div style="margin-bottom: 20px;">
                <label style="display: block; color: #666; font-weight: 600; margin-bottom: 10px;">Mot de passe:</label>
                <input type="password" id="passwordInput" placeholder="Entrez le mot de passe" onkeypress="if(event.key==='Enter') verifyPassword()" style="width: 100%; padding: 12px 15px; border: 2px solid #e0e0e0; border-radius: 10px; font-size: 1em;">
            </div>
            
            <div class="modal-buttons">
                <button class="button btn-primary" onclick="verifyPassword()">Valider</button>
                <button class="button btn-secondary" onclick="cancelPassword()">Annuler</button>
            </div>
        </div>
    </div>
    
    <!-- NOTIFICATION TOAST -->
    <div class="notification-toast" id="notificationToast"></div>

    <script>
        // ===== INITIALISATION LOCALSTORAGE =====
        if (!localStorage.getItem('initialized')) {
            localStorage.clear();
            localStorage.setItem('initialized', 'true');
        }

        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let users = JSON.parse(localStorage.getItem('allUsers')) || [];
        let events = JSON.parse(localStorage.getItem('agendaEvents')) || [];
        let notifications = JSON.parse(localStorage.getItem('agendaNotifications')) || [];
        let bulletins = JSON.parse(localStorage.getItem('bulletins')) || [];
        
        let currentDate = new Date();
        let selectedDate = new Date();
        let currentDateProf = new Date();
        let selectedDateProf = new Date();
        let currentFilter = 'all';
        let currentFilterProf = 'all';
        let searchQuery = '';
        let searchQueryProf = '';
        let currentRole = 'eleve';
        let selectedAvatarFile = null;
        let selectedPdfFile = null;
        
        function saveToLocalStorage() {
            try {
                if (currentUser) {
                    localStorage.setItem('currentUser', JSON.stringify(currentUser));
                }
                localStorage.setItem('allUsers', JSON.stringify(users));
                localStorage.setItem('agendaEvents', JSON.stringify(events));
                localStorage.setItem('agendaNotifications', JSON.stringify(notifications));
                localStorage.setItem('bulletins', JSON.stringify(bulletins));
            } catch (e) {
                console.error('Erreur localStorage:', e);
            }
        }
        
        function handleAvatarSelect() {
            const fileInput = document.getElementById('registerAvatarFile');
            const avatarLabel = document.getElementById('avatarLabel');
            
            if (fileInput.files && fileInput.files[0]) {
                const file = fileInput.files[0];
                selectedAvatarFile = file;
                
                const fileName = file.name;
                avatarLabel.classList.add('has-file');
                avatarLabel.innerHTML = `<span>✅</span><p>${fileName}</p>`;
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('avatarPreviewContainer').innerHTML = `<div class="avatar-preview-register"><img src="${e.target.result}" alt="Avatar"></div>`;
                };
                reader.readAsDataURL(file);
            }
        }
        
        function handleFileSelect() {
            const fileInput = document.getElementById('bulletinFile');
            const fileLabel = document.getElementById('fileLabel');
            
            if (fileInput.files && fileInput.files[0]) {
                const fileName = fileInput.files[0].name;
                selectedPdfFile = fileInput.files[0];
                fileLabel.classList.add('has-file');
                fileLabel.innerHTML = `<span>✅</span><span>${fileName}</span>`;
            }
        }
        
        function changeProfileAvatar() {
            const fileInput = document.getElementById('profileAvatarFile');
            
            if (fileInput.files && fileInput.files[0]) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    currentUser.avatar = e.target.result;
                    saveToLocalStorage();
                    updateUserProfile();
                    showNotification('✅ Avatar changé!', 'success');
                };
                reader.readAsDataURL(fileInput.files[0]);
            }
        }
        
        function switchToRegister() {
            document.getElementById('loginForm').classList.add('hidden');
            document.getElementById('registerForm').classList.remove('hidden');
            document.getElementById('authTitle').textContent = '✍️ Créer un Compte';
            selectedAvatarFile = null;
            resetAvatarPreview();
        }
        
        function resetAvatarPreview() {
            document.getElementById('registerAvatarFile').value = '';
            document.getElementById('avatarLabel').classList.remove('has-file');
            document.getElementById('avatarLabel').innerHTML = '<span>📸</span><p>Clique pour ajouter une photo</p>';
            document.getElementById('avatarPreviewContainer').innerHTML = '<div class="avatar-preview-register">👤</div>';
        }
        
        function switchToLogin() {
            document.getElementById('registerForm').classList.add('hidden');
            document.getElementById('loginForm').classList.remove('hidden');
            document.getElementById('authTitle').textContent = '📖 Connexion';
        }
        
        function register() {
            const name = document.getElementById('registerName').value.trim();
            const email = document.getElementById('registerEmail').value.trim();
            const password = document.getElementById('registerPassword').value;
            const password2 = document.getElementById('registerPassword2').value;
            const classe = document.getElementById('registerClass').value;
            
            if (!name || !email || !password || !password2 || !classe) {
                showNotification('❌ Remplis tous les champs!', 'error');
                return;
            }
            
            if (password !== password2) {
                showNotification('❌ Les mots de passe ne correspondent pas!', 'error');
                return;
            }
            
            if (users.some(u => u.email === email)) {
                showNotification('❌ Cet email est déjà utilisé!', 'error');
                return;
            }
            
            if (selectedAvatarFile) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const avatarDataUrl = e.target.result;
                    createUserWithAvatar(name, email, password, classe, avatarDataUrl);
                };
                reader.readAsDataURL(selectedAvatarFile);
            } else {
                createUserWithAvatar(name, email, password, classe, null);
            }
        }
        
        function createUserWithAvatar(name, email, password, classe, avatar) {
            const user = {
                id: Date.now(),
                name,
                email,
                password,
                classe,
                avatar: avatar || null,
                initials: name.charAt(0).toUpperCase()
            };
            
            users.push(user);
            saveToLocalStorage();
            
            showNotification('✅ Compte créé! Connecte-toi maintenant.', 'success');
            switchToLogin();
            resetRegisterForm();
        }
        
        function resetRegisterForm() {
            document.getElementById('registerName').value = '';
            document.getElementById('registerEmail').value = '';
            document.getElementById('registerPassword').value = '';
            document.getElementById('registerPassword2').value = '';
            document.getElementById('registerClass').value = '';
            resetAvatarPreview();
            selectedAvatarFile = null;
        }
        
        function login() {
            const email = document.getElementById('loginEmail').value.trim();
            const password = document.getElementById('loginPassword').value;
            
            if (!email || !password) {
                showNotification('❌ Remplis email et mot de passe!', 'error');
                return;
            }
            
            const user = users.find(u => u.email === email && u.password === password);
            
            if (!user) {
                showNotification('❌ Email ou mot de passe incorrect!', 'error');
                return;
            }
            
            currentUser = user;
            saveToLocalStorage();
            showNotification('✅ Connecté avec succès!', 'success');
            showApp();
        }
        
        function logout() {
            if (confirm('Sûr de vouloir te déconnecter?')) {
                currentUser = null;
                localStorage.removeItem('currentUser');
                showNotification('👋 Déconnecté!', 'success');
                showAuth();
            }
        }
        
        function showAuth() {
            document.getElementById('authContainer').classList.remove('hidden');
            document.getElementById('mainApp').classList.add('hidden');
        }
        
        function showApp() {
            document.getElementById('authContainer').classList.add('hidden');
            document.getElementById('mainApp').classList.remove('hidden');
            updateUserProfile();
            initEleve();
        }
        
        function updateUserProfile() {
            document.getElementById('userName').textContent = currentUser.name;
            document.getElementById('userClass').textContent = 'Classe: ' + currentUser.classe;
            
            const userAvatarEl = document.getElementById('userAvatar');
            if (currentUser.avatar) {
                userAvatarEl.innerHTML = `<img src="${currentUser.avatar}" alt="Avatar"><div class="user-avatar-edit">✏️</div>`;
            } else {
                userAvatarEl.innerHTML = `<div id="userAvatarContent">${currentUser.initials}</div><div class="user-avatar-edit">✏️</div>`;
            }
        }
        
        function showNotification(message, type) {
            const notification = document.getElementById('notificationToast');
            notification.textContent = message;
            notification.className = `notification-toast ${type} show`;
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        function isEventExpired(eventDate) {
            const today = new Date();
            today.setHours(0, 0, 0, 0);
            const event = new Date(eventDate);
            return event < today;
        }
        
        function selectRole(role) {
            document.querySelectorAll('[id$="View"]').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('.role-btn').forEach(btn => btn.classList.remove('active'));
            
            const roleIndex = {'eleve': 0, 'professeur': 1, 'bulletin': 2, 'notifications': 3}[role];
            document.querySelectorAll('.role-btn')[roleIndex]?.classList.add('active');
            
            if (role === 'eleve') {
                document.getElementById('eleveView').classList.remove('hidden');
                initEleve();
            } else if (role === 'professeur') {
                document.getElementById('passwordModal').classList.add('show');
            } else if (role === 'bulletin') {
                document.getElementById('bulletinView').classList.remove('hidden');
                loadBulletinsForStudent();
            } else if (role === 'notifications') {
                document.getElementById('notificationsView').classList.remove('hidden');
                displayNotifications();
                updateNotificationsStats();
            }
        }
        
        function verifyPassword() {
            const password = document.getElementById('passwordInput').value;
            
            if (password === '9876') {
                document.getElementById('passwordModal').classList.remove('show');
                document.getElementById('passwordInput').value = '';
                
                currentRole = 'professeur';
                document.querySelectorAll('.role-btn').forEach(btn => btn.classList.remove('active'));
                document.querySelectorAll('.role-btn')[1].classList.add('active');
                
                document.getElementById('eleveView').classList.add('hidden');
                document.getElementById('professeurView').classList.remove('hidden');
                
                showNotification('✅ Accès autorisé!', 'success');
                initProfesseur();
            } else {
                showNotification('❌ Mot de passe incorrect!', 'error');
                document.getElementById('passwordInput').value = '';
                document.getElementById('passwordInput').focus();
            }
        }
        
        function cancelPassword() {
            document.getElementById('passwordModal').classList.remove('show');
            document.getElementById('passwordInput').value = '';
            document.querySelectorAll('.role-btn')[0].classList.add('active');
            document.querySelectorAll('.role-btn')[1].classList.remove('active');
        }
        
        // ===== ÉLÈVE =====
        function initEleve() {
            renderCalendar();
            displayTasks();
            updateStats();
        }
        
        function renderCalendar() {
            const year = currentDate.getFullYear();
            const month = currentDate.getMonth();
            
            document.getElementById('currentMonth').textContent = 
                currentDate.toLocaleDateString('fr-FR', { month: 'long', year: 'numeric' });
            
            const firstDay = new Date(year, month, 1);
            const startDate = new Date(firstDay);
            startDate.setDate(startDate.getDate() - firstDay.getDay() + 1);
            
            const daysGrid = document.getElementById('daysGrid');
            daysGrid.innerHTML = '';
            
            let currentDateLoop = new Date(startDate);
            const today = new Date();
            today.setHours(0, 0, 0, 0);
            
            for (let i = 0; i < 42; i++) {
                const day = document.createElement('div');
                day.className = 'day';
                day.textContent = currentDateLoop.getDate();
                
                if (currentDateLoop.getMonth() !== month) {
                    day.classList.add('other-month');
                }
                
                if (currentDateLoop.toDateString() === new Date().toDateString()) {
                    day.classList.add('today');
                }
                
                if (currentDateLoop.toDateString() === selectedDate.toDateString()) {
                    day.classList.add('selected');
                }
                
                const dateStr = currentDateLoop.toISOString().split('T')[0];
                if (events.some(e => e.date === dateStr && e.classe === currentUser.classe && !isEventExpired(e.date))) {
                    day.classList.add('has-event');
                }
                
                const dateObj = new Date(currentDateLoop);
                day.onclick = () => selectDate(dateObj);
                
                daysGrid.appendChild(day);
                currentDateLoop.setDate(currentDateLoop.getDate() + 1);
            }
        }
        
        function previousMonth() {
            currentDate.setMonth(currentDate.getMonth() - 1);
            renderCalendar();
        }
        
        function nextMonth() {
            currentDate.setMonth(currentDate.getMonth() + 1);
            renderCalendar();
        }
        
        function selectDate(date) {
            selectedDate = new Date(date);
            renderCalendar();
            displayTasks();
        }
        
        function goToToday() {
            currentDate = new Date();
            selectedDate = new Date();
            renderCalendar();
            displayTasks();
        }
        
        function displayTasks() {
            const selectedDateStr = selectedDate.toISOString().split('T')[0];
            let filtered = events.filter(e => 
                e.date === selectedDateStr && 
                e.classe === currentUser.classe && 
                !isEventExpired(e.date)
            );
            
            if (currentFilter !== 'all') {
                filtered = filtered.filter(e => e.type === currentFilter);
            }
            
            if (searchQuery) {
                filtered = filtered.filter(e => 
                    e.title.toLowerCase().includes(searchQuery) ||
                    e.subject.toLowerCase().includes(searchQuery) ||
                    e.description.toLowerCase().includes(searchQuery)
                );
            }
            
            filtered.sort((a, b) => a.time.localeCompare(b.time));
            
            const container = document.getElementById('tasksContainer');
            
            if (filtered.length === 0) {
                container.innerHTML = '<div class="no-events">Aucune tâche pour ce jour</div>';
                return;
            }
            
            container.innerHTML = filtered.map(e => `
                <div class="event-item ${e.type}">
                    <div class="event-header">
                        <div class="event-title">${e.title}</div>
                        <span class="event-type ${e.type}">${getTypeLabel(e.type)}</span>
                    </div>
                    <div class="event-subject">${e.subject}</div>
                    <div class="event-time">🕐 ${e.time}</div>
                    ${e.professor ? `<div class="event-professor">👨‍🏫 ${e.professor}</div>` : ''}
                    ${e.description ? `<div class="event-description">${e.description}</div>` : ''}
                </div>
            `).join('');
        }
        
        function filterTasks(type) {
            currentFilter = type;
            document.querySelectorAll('#eleveView .filter-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            displayTasks();
        }
        
        function filterTasksSearch() {
            searchQuery = document.getElementById('searchBox').value.toLowerCase();
            displayTasks();
        }
        
        function updateStats() {
            const classEvents = events.filter(e => e.classe === currentUser.classe && !isEventExpired(e.date));
            document.getElementById('totalTasks').textContent = classEvents.length;
            document.getElementById('homeworkCount').textContent = classEvents.filter(e => e.type === 'homework').length;
            document.getElementById('examCount').textContent = classEvents.filter(e => e.type === 'exam').length;
            
            const today = new Date().toISOString().split('T')[0];
            const upcoming = classEvents.filter(e => e.date >= today).length;
            document.getElementById('upcomingCount').textContent = upcoming;
        }
        
        // ===== PROFESSEUR =====
        function initProfesseur() {
            renderCalendarProf();
            displayEvents();
            updateStatsProfesseur();
            document.getElementById('eventDate').valueAsDate = new Date();
            loadStudentsForProfessor();
            resetBulletinForm();
        }
        
        function resetBulletinForm() {
            selectedPdfFile = null;
            document.getElementById('bulletinFile').value = '';
            document.getElementById('fileLabel').classList.remove('has-file');
            document.getElementById('fileLabel').innerHTML = '<span>📎</span><span>Clique pour ajouter un PDF</span>';
        }
        
        function renderCalendarProf() {
            const year = currentDateProf.getFullYear();
            const month = currentDateProf.getMonth();
            
            document.getElementById('currentMonthProf').textContent = 
                currentDateProf.toLocaleDateString('fr-FR', { month: 'long', year: 'numeric' });
            
            const firstDay = new Date(year, month, 1);
            const startDate = new Date(firstDay);
            startDate.setDate(startDate.getDate() - firstDay.getDay() + 1);
            
            const daysGrid = document.getElementById('daysGridProf');
            daysGrid.innerHTML = '';
            
            let currentDateLoop = new Date(startDate);
            
            for (let i = 0; i < 42; i++) {
                const day = document.createElement('div');
                day.className = 'day';
                day.textContent = currentDateLoop.getDate();
                
                if (currentDateLoop.getMonth() !== month) {
                    day.classList.add('other-month');
                }
                
                if (currentDateLoop.toDateString() === new Date().toDateString()) {
                    day.classList.add('today');
                }
                
                const dateStr = currentDateLoop.toISOString().split('T')[0];
                if (events.some(e => e.date === dateStr)) {
                    day.classList.add('has-event');
                }
                
                daysGrid.appendChild(day);
                currentDateLoop.setDate(currentDateLoop.getDate() + 1);
            }
        }
        
        function previousMonthProf() {
            currentDateProf.setMonth(currentDateProf.getMonth() - 1);
            renderCalendarProf();
        }
        
        function nextMonthProf() {
            currentDateProf.setMonth(currentDateProf.getMonth() + 1);
            renderCalendarProf();
        }
        
        function goToTodayProf() {
            currentDateProf = new Date();
            renderCalendarProf();
        }
        
        function addEvent() {
            const title = document.getElementById('eventTitle').value.trim();
            const date = document.getElementById('eventDate').value;
            const time = document.getElementById('eventTime').value;
            const classe = document.getElementById('eventClass').value;
            const subject = document.getElementById('eventSubject').value;
            const type = document.getElementById('eventType').value;
            const description = document.getElementById('eventDescription').value.trim();
            
            if (!title || !date || !classe || !subject) {
                showNotification('❌ Remplis tous les champs obligatoires!', 'error');
                return;
            }
            
            const event = {
                id: Date.now(),
                title,
                date,
                time: time || '00:00',
                classe,
                subject,
                type,
                description,
                professor: currentUser.name,
                completed: false
            };
            
            events.push(event);
            saveToLocalStorage();
            
            document.getElementById('eventTitle').value = '';
            document.getElementById('eventDescription').value = '';
            document.getElementById('eventSubject').value = '';
            document.getElementById('eventClass').value = '';
            document.getElementById('eventTime').value = '';
            document.getElementById('eventType').value = 'homework';
            document.getElementById('eventDate').valueAsDate = new Date();
            
            showNotification('✅ Événement ajouté!', 'success');
            displayEvents();
            renderCalendarProf();
            updateStatsProfesseur();
        }
        
        function displayEvents() {
            let filtered = events;
            
            if (currentFilterProf !== 'all') {
                filtered = filtered.filter(e => e.type === currentFilterProf);
            }
            
            if (searchQueryProf) {
                filtered = filtered.filter(e => 
                    e.title.toLowerCase().includes(searchQueryProf) ||
                    e.subject.toLowerCase().includes(searchQueryProf) ||
                    e.classe.toLowerCase().includes(searchQueryProf) ||
                    e.description.toLowerCase().includes(searchQueryProf)
                );
            }
            
            filtered.sort((a, b) => new Date(a.date) - new Date(b.date));
            
            const container = document.getElementById('eventsContainer');
            
            if (filtered.length === 0) {
                container.innerHTML = '<div class="no-events">Aucun événement créé</div>';
                return;
            }
            
            container.innerHTML = filtered.map(e => `
                <div class="event-item ${e.type}">
                    <div class="event-header">
                        <div class="event-title">${e.title}</div>
                        <span class="event-type ${e.type}">${getTypeLabel(e.type)}</span>
                    </div>
                    <div class="event-subject">${e.subject}</div>
                    <div class="event-time">📚 Classe: ${e.classe}</div>
                    <div class="event-time">🕐 ${e.time}</div>
                    ${e.description ? `<div class="event-description">${e.description}</div>` : ''}
                </div>
            `).join('');
        }
        
        function filterEventsProfesseur(type) {
            currentFilterProf = type;
            document.querySelectorAll('#professeurView .filter-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            displayEvents();
        }
        
        function filterEventsSearch() {
            searchQueryProf = document.getElementById('searchBoxProf').value.toLowerCase();
            displayEvents();
        }
        
        function getTypeLabel(type) {
            const labels = {
                'homework': '📝 DEVOIR',
                'exam': '📋 EXAMEN',
                'test': '✏️ TEST',
                'project': '🎯 PROJET'
            };
            return labels[type] || type;
        }
        
        function updateStatsProfesseur() {
            document.getElementById('totalEvents').textContent = events.length;
            document.getElementById('homeworkCountProf').textContent = events.filter(e => e.type === 'homework').length;
            document.getElementById('examCountProf').textContent = events.filter(e => e.type === 'exam').length;
            
            const today = new Date().toISOString().split('T')[0];
            const upcoming = events.filter(e => e.date >= today).length;
            document.getElementById('upcomingCountProf').textContent = upcoming;
        }
        
        // ===== BULLETIN =====
        function loadStudentsForProfessor() {
            const select = document.getElementById('bulletinStudent');
            const classStudents = users.filter(u => u.classe === currentUser.classe);
            
            select.innerHTML = '<option value="">Choisir un élève...</option>';
            classStudents.forEach(student => {
                const option = document.createElement('option');
                option.value = student.id;
                option.textContent = student.name;
                select.appendChild(option);
            });
        }
        
        function sendBulletin() {
            const studentId = document.getElementById('bulletinStudent').value;
            const bulletinName = document.getElementById('bulletinName').value.trim();
            
            if (!studentId || !selectedPdfFile || !bulletinName) {
                showNotification('❌ Remplis tous les champs!', 'error');
                return;
            }
            
            if (selectedPdfFile.type !== 'application/pdf') {
                showNotification('❌ Seuls les fichiers PDF sont acceptés!', 'error');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = function(e) {
                const bulletin = {
                    id: Date.now(),
                    name: bulletinName,
                    studentId: parseInt(studentId),
                    professorId: currentUser.id,
                    professorName: currentUser.name,
                    fileData: e.target.result,
                    fileName: selectedPdfFile.name,
                    sentDate: new Date().toLocaleString('fr-FR')
                };
                
                bulletins.push(bulletin);
                saveToLocalStorage();
                
                showNotification('✅ Bulletin envoyé!', 'success');
                
                document.getElementById('bulletinStudent').value = '';
                document.getElementById('bulletinName').value = '';
                resetBulletinForm();
            };
            reader.readAsDataURL(selectedPdfFile);
        }
        
        function loadBulletinsForStudent() {
            const container = document.getElementById('bulletinsContainer');
            const myBulletins = bulletins.filter(b => b.studentId === currentUser.id);
            
            if (myBulletins.length === 0) {
                container.innerHTML = '<div class="no-events">Aucun bulletin reçu</div>';
                document.getElementById('totalBulletins').textContent = 0;
                return;
            }
            
            container.innerHTML = myBulletins.map(b => `
                <div class="event-item">
                    <div class="event-header">
                        <div class="event-title">${b.name}</div>
                        <span class="event-type">📄 PDF</span>
                    </div>
                    <div class="event-recipient">👨‍🏫 De: ${b.professorName}</div>
                    <div class="event-recipient">📅 ${b.sentDate}</div>
                    <a href="${b.fileData}" download="${b.fileName}" class="pdf-link">📥 Télécharger</a>
                </div>
            `).join('');
            
            document.getElementById('totalBulletins').textContent = myBulletins.length;
        }
        
        // ===== NOTIFICATIONS =====
        function addNotification() {
            const title = document.getElementById('notifTitle').value.trim();
            const message = document.getElementById('notifMessage').value.trim();
            const type = document.getElementById('notifType').value;
            
            if (!title || !message) {
                showNotification('❌ Remplis tous les champs!', 'error');
                return;
            }
            
            const notification = {
                id: Date.now(),
                title,
                message,
                type,
                createdAt: new Date().toLocaleString('fr-FR')
            };
            
            notifications.push(notification);
            saveToLocalStorage();
            
            document.getElementById('notifTitle').value = '';
            document.getElementById('notifMessage').value = '';
            document.getElementById('notifType').value = 'normal';
            
            showNotification('✅ Notification envoyée!', 'success');
        }
        
        function displayNotifications() {
            const container = document.getElementById('notificationsContainer');
            
            if (notifications.length === 0) {
                container.innerHTML = '<div class="no-events">Aucune notification</div>';
                return;
            }
            
            container.innerHTML = [...notifications].reverse().map(n => `
                <div class="event-item">
                    <div class="event-header">
                        <div class="event-title">${n.title}</div>
                        <span class="event-type ${n.type === 'important' ? 'exam' : 'homework'}">${n.type === 'important' ? '⚠️ IMPORTANT' : '📢 NORMAL'}</span>
                    </div>
                    <div class="event-description">${n.message}</div>
                    <div class="event-time">⏰ ${n.createdAt}</div>
                </div>
            `).join('');
        }
        
        function updateNotificationsStats() {
            document.getElementById('totalNotifications').textContent = notifications.length;
            document.getElementById('importantNotifications').textContent = notifications.filter(n => n.type === 'important').length;
        }
        
        // ===== INITIALISATION =====
        if (currentUser) {
            showApp();
        } else {
            showAuth();
        }
    </script>
</body>
</html>
