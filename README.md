<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Menu Picker</title>
    <style>
        /* 设置背景图片 */
        body {
            font-family: '华文行楷', 'KaiTi', sans-serif; /* 使用华文行楷，如果没有则使用楷体 */
            background: url('your-repo/beijing.jpg') no-repeat center center fixed; /* 替换为你的相对路径 */
            background-size: cover; /* 背景图像覆盖整个页面 */
            height: 100vh; /* 设置视口高度 */
            margin: 0;
        }

        /* 创建一个半透明的覆盖层 */
        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5); /* 黑色半透明 */
            z-index: -1; /* 让它在内容下方 */
        }

        /* 容器样式 */
        .container {
            text-align: center;
            padding: 30px;
            background-color: rgba(255, 255, 255, 0.85); /* 半透明白色背景 */
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            width: 80%;
            max-width: 500px;
        }

        h1 {
            font-size: 2.2em;
            color: #333;
            margin-bottom: 20px;
            font-weight: bold;
        }

        /* 菜单显示的文字 */
        #menu {
            font-size: 1.8em;
            color: #6c5b7b;
            margin: 20px 0;
            font-weight: 600;
            min-height: 50px;
        }

        /* 按钮样式 */
        button {
            padding: 12px 30px;
            font-size: 1.1em;
            background-color: #f67280;
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        button:hover {
            background-color: #c06c84;
            transform: translateY(-3px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
        }

        button:active {
            transform: translateY(2px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>关于填饱肚子这件事</h1>
        <div id="menu">快快显灵</div>
        <button onclick="pickMenu()">揭晓答案</button>
    </div>

    <script>
        // 定义菜单选项
        const menuItems = [
            "鸡公煲",
            "凉皮肉夹馍",
            "酱骨头",
            "梨花汤饭",
            "肠粉",
            "袁记水饺",
            "超意兴",
            "螺蛳粉",
            "煎饼果子",
            "面条"
        ];

        // 随机选择菜单项的函数
        function pickMenu() {
            const randomIndex = Math.floor(Math.random() * menuItems.length);
            const selectedMenu = menuItems[randomIndex];
            document.getElementById("menu").innerText = "今日份饭饭: " + selectedMenu;
        }
    </script>
</body>
</html>

