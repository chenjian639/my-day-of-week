<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>今天是周几？</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Helvetica Neue', Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
        }
        .container {
            background: rgba(255, 255, 255, 0.1);
            padding: 3rem;
            border-radius: 1rem;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
        }
        h1 {
            font-size: 4rem;
            margin-bottom: 0.5rem;
        }
        p {
            font-size: 1.5rem;
            margin-top: 0;
            opacity: 0.9;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 id="dayOfWeek"></h1>
        <p id="fullDate"></p>
    </div>

    <script>
        // 创建一个Date对象获取当前时间
        const today = new Date();
        
        // 获取星期几 (0 代表周日, 1 代表周一, ..., 6 代表周六)
        const dayOfWeekNumber = today.getDay();
        
        // 创建一个星期几的中文字符串数组
        const weekdays = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
        
        // 根据数字获取对应的星期几中文
        const dayOfWeekStr = weekdays[dayOfWeekNumber];
        
        // 将结果显示在页面上
        document.getElementById('dayOfWeek').textContent = dayOfWeekStr;
        
        // 可选：显示完整的日期时间
        const options = { year: 'numeric', month: 'long', day: 'numeric', weekday: 'long' };
        document.getElementById('fullDate').textContent = today.toLocaleDateString('zh-CN', options);
    </script>
</body>
</html>
