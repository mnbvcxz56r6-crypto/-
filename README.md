<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أدواتي - تطبيق استئجار الأدوات</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #2E7D32;
            --secondary: #4CAF50;
            --accent: #FF9800;
            --light: #F5F5F5;
            --dark: #333;
            --gray: #757575;
        }

        body {
            background-color: #f8f9fa;
            color: var(--dark);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* التصميم العام */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: var(--primary);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: var(--primary);
        }

        .user-actions a {
            margin-right: 15px;
            text-decoration: none;
            color: var(--dark);
        }

        .user-actions .btn {
            background-color: var(--primary);
            color: white;
            padding: 8px 15px;
            border-radius: 4px;
            text-decoration: none;
        }

        /* الصفحة الرئيسية */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://via.placeholder.com/1200x400') no-repeat center center;
            background-size: cover;
            color: white;
            padding: 80px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 36px;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 18px;
            margin-bottom: 30px;
        }

        .search-box {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
        }

        .search-box input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 4px 0 0 4px;
        }

        .search-box button {
            background-color: var(--accent);
            color: white;
            border: none;
            padding: 0 20px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
        }

        .categories {
            padding: 50px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 30px;
            font-size: 28px;
            color: var(--dark);
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 20px;
        }

        .category-card {
            background-color: white;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.3s;
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-5px);
        }

        .category-icon {
            font-size: 30px;
            margin-bottom: 10px;
            color: var(--primary);
        }

        .tools-section {
            padding: 50px 0;
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
        }

        .tool-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .tool-card:hover {
            transform: translateY(-5px);
        }

        .tool-image {
            height: 180px;
            background-color: #eee;
            background-size: cover;
            background-position: center;
        }

        .tool-info {
            padding: 15px;
        }

        .tool-name {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .tool-price {
            color: var(--primary);
            font-weight: bold;
            margin-bottom: 10px;
        }

        .tool-rating {
            color: var(--accent);
            margin-bottom: 10px;
        }

        .tool-actions {
            display: flex;
            justify-content: space-between;
        }

        .btn {
            padding: 8px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
        }

        .btn-primary {
            background-color: var(--primary);
            color: white;
        }

        .btn-outline {
            background-color: transparent;
            border: 1px solid var(--primary);
            color: var(--primary);
        }

        footer {
            background-color: var(--dark);
            color: white;
            padding: 40px 0;
            margin-top: 50px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
        }

        .footer-column h3 {
            margin-bottom: 20px;
            font-size: 18px;
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column ul li {
            margin-bottom: 10px;
        }

        .footer-column ul li a {
            color: #ddd;
            text-decoration: none;
        }

        .footer-column ul li a:hover {
            color: white;
        }

        .copyright {
            text-align: center;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid #444;
        }

        /* تصميم الصفحات الأخرى */
        .page {
            display: none;
            padding: 30px 0;
        }

        .page.active {
            display: block;
        }

        .page-title {
            margin-bottom: 20px;
            font-size: 28px;
            color: var(--dark);
        }

        .tool-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        .tool-gallery img {
            width: 100%;
            border-radius: 8px;
        }

        .tool-description {
            margin: 20px 0;
        }

        .tool-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: bold;
        }

        .status-available {
            background-color: #E8F5E9;
            color: var(--primary);
        }

        .rent-form {
            max-width: 500px;
            margin-top: 30px;
        }

        .form-group {
            margin-bottom:
