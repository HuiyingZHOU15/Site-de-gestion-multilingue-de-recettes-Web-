# 🍽️ Projet Web : Site de gestion multilingue de recettes  Web 项目：多语言菜谱管理系统

Ce projet est un site web dynamique permettant aux utilisateurs de créer, consulter, modifier, traduire et gérer des recettes en français et en anglais. Il inclut une gestion de rôles avancée (Chef, Traducteur, Admin). 本项目是一个动态 Web 应用，支持用户创建、查看、修改、翻译和管理菜谱内容，支持法语 / 英语双语展示，并实现了较完整的角色与权限管理机制（Chef、Traducteur、Admin）。

## 🌐 Fonctionnalités principales

- 🔐 Authentification / Inscription 用户注册 / 登录
- 👨‍🍳 Création, modification, suppression des recettes (Chef) 菜谱的创建、修改与删除（Chef）
- 🌍 Traduction bilingue des recettes (Traducteur ou Admin) 菜谱的双语翻译功能（Traducteur 或 Admin）
- 🧾 Interface détaillée par recette 单个菜谱的详细展示页面
- 🧑‍💼 Gestion des utilisateurs et des rôles (Admin) 用户与角色管理（Admin）
- ❤️ Commentaires, likes, et filtres diététiques  评论、点赞及饮食偏好筛选
- 🖼️ Ajout / suppression d’images de recette 菜谱图片的添加与删除
- 📊 Statistiques de l'application (Admin) 应用统计信息展示（Admin）

---

## 📁 Structure du projet 項目結構

```
projet/
│
├── back/                     # Backend PHP (API) 后端
│   ├── controllers/          # Contrôleurs PHP PHP 控制器
│   │   ├── AuthController.php      # Connexion / inscription 登录/注册
│   │   ├── RecipeController.php    # Gestion des recettes 菜谱管理
│   │   └── AdminController.php     # Rôles, validation 角色与校验
│   ├── data/                 # Données persistées (JSON) 数据存储(JSON)
│   └── index.php            # Routeur principal (API) 后端主路由
│
├── front/                   # Interface utilisateur (Frontend) 前端界面
│   ├── assets/ 
│   │   ├── css/             # Feuilles de style 样式文件
│   │   └── js/              # Scripts JS (optionnel) JavaScript脚本
│   ├── auth/                # Pages de connexion / inscription 登录/注册页面
│   ├── admin/               # Espace admin (gestion utilisateurs, recettes) 管理员界面
│   ├── chef/                # Pages spécifiques au rôle Chef 主厨专属界面
│   ├── dashboard.html       # Tableau de bord multirôle 多角色仪表盘
│   ├── index.html           # Page d’accueil 首页
│   ├── recipes.html         # Liste de toutes les recettes 菜谱列表
│   ├── recipe_details.html  # Détail d’une recette 菜谱详情页
│   └── translation.html     # Interface spéciale de traduction à 2 colonnes 双拦翻译界面
```



##👥 Gestion des rôles

| Rôle         | Permissions                                                                                                                                     |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `Cuisinier` 普通用户 | Accès public uniquement 仅访问公开内容                                                                                                    |
| `Chef`主厨       | Ajouter / modifier / supprimer ses recettes 添加/修改/删除自己的菜谱                                                                          |
| `Traducteur`译者 | Traduire uniquement les champs vides des recettes validées, sauf s’il est aussi Chef (alors tout modifier dans ses propres recettes) 仅可翻译已验证菜谱中尚未翻译的字段（若同时具备 Chef 角色，可修改自己的菜谱）                                                                      |
| `Admin` 管理员     | Gérer les utilisateurs, valider les recettes, traduire, modifier toutes les recettes, supprimer n’importe quelle recette, voir les statistiques用户与角色管理、菜谱验证、全局翻译与修改、删除任意菜谱、查看统计数据                                                                             |

---

## ⚙️ Lancer le projet localement 本地运行方式

1. Cloner le dépôt 克隆项目
2. Lancer un serveur PHP : 启动本地服务器
   ```bash
   php -S localhost:8000
Accéder à :


http://localhost:8000/front/auth/login.html 浏览器访问
🧪 Accès test rapide 测试账号：
测试账号定义在这个文件
Dans le fichier back/data/users.json : 
 
Nom d'utilisateur	用户名 Mot de passe 密码	Rôles 角色
admin	admin	["Admin", "Traducteur"]
chef1	test	["Chef"]
trad1	test	["Traducteur"]

📌 Notes techniques 技术说明
Toutes les données sont enregistrées dans des fichiers .json 所有数据基于 .json 文件进行持久化存储

Les appels frontend vers le backend utilisent fetch ou $.ajax (jQuery) 前端与后端通过 fetch / $.ajax (jQuery) 进行通信

Chaque fonctionnalité respecte les permissions selon les rôles 所有功能均基于角色权限进行访问控制

L’interface de traduction est responsive et conforme aux consignes d'affichage bilingue 翻译界面采用双栏布局，支持响应式显示，符合双语展示规范


👨‍💻 Réalisé par  项目信息 ：
Projet académique réalisé par Huiying et Massyl, dans le cadre du cours Programmation Web - L3 MIAGE. Université Paris Saclay
本项目为 法国巴黎萨克类大学 MIAGE（信息与企业管理）专业 Web 编程课程项目，
由 Huiying Zhou & Massyl 完成

### 🚀 Démo en ligne 在线演示点击下面链接

🖥️ [https://drive.google.com/file/d/1iIHh9cugGrvGLhaTnvb0t5ot2MFq25fD/view?usp=drive_link)


