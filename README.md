<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>服务器验证</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <style>
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        .pulse {
            animation: pulse 2s infinite;
        }
        .fade-in {
            animation: fadeIn 1s ease-in;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .slide-up {
            animation: slideUp 0.5s ease-out;
        }
        @keyframes slideUp {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
    </style>
</head>
<body class="bg-gray-100 min-h-screen flex items-center justify-center p-4 transition-colors duration-500">
    <div id="verification" class="bg-white rounded-xl shadow-lg p-8 max-w-md w-full text-center fade-in">
        <div class="text-5xl mb-6 text-blue-500 pulse">
            <i class="fa fa-shield"></i>
        </div>
        <h1 class="text-2xl font-bold text-gray-800 mb-4">服务器验证中</h1>
        <p class="text-gray-600 mb-6">正在验证您的身份信息，请稍候...</p>
        <div class="w-full bg-gray-200 rounded-full h-2.5">
            <div id="progress-bar" class="bg-blue-500 h-2.5 rounded-full" style="width: 0%"></div>
        </div>
        <p id="countdown" class="mt-4 text-gray-500">5秒后完成验证</p>
    </div>

    <div id="error" class="hidden bg-white rounded-xl shadow-lg p-8 max-w-md w-full text-center fade-in">
        <div class="text-5xl mb-6 text-red-500 pulse">
            <i class="fa fa-exclamation-triangle"></i>
        </div>
        <h1 class="text-2xl font-bold text-red-600 mb-4">身份异常</h1>
        <p class="text-gray-700 mb-6">您的身份验证未通过，疑似异常访问</p>
        <p class="text-lg text-gray-800 font-medium">请联系站长解除限制</p>
        <button id="contact-btn" class="mt-6 bg-red-500 hover:bg-red-600 text-white font-bold py-2 px-6 rounded-full transition duration-300">
            <i class="fa fa-envelope mr-2"></i>联系站长
        </button>
        <div id="qq-number" class="hidden mt-6 p-4 bg-red-50 rounded-lg slide-up">
            <p class="text-gray-800"><i class="fa fa-qq text-blue-500 mr-2"></i>站长QQ：101345414</p>
        </div>
    </div>

    <script>
        // 进度条和倒计时逻辑
        let progress = 0;
        const progressBar = document.getElementById('progress-bar');
        const countdownEl = document.getElementById('countdown');
        const totalSeconds = 5;
        let secondsLeft = totalSeconds;
        
        // 每100毫秒更新一次进度条
        const interval = setInterval(() => {
            progress += (100 / (totalSeconds * 10));
            progressBar.style.width = `${progress}%`;
            
            secondsLeft = Math.ceil(totalSeconds - (progress / 100) * totalSeconds);
            countdownEl.textContent = `${secondsLeft}秒后完成验证`;
            
            if (progress >= 100) {
                clearInterval(interval);
                // 显示错误信息
                document.getElementById('verification').classList.add('hidden');
                document.getElementById('error').classList.remove('hidden');
                // 页面背景渐变为红色调
                document.body.classList.remove('bg-gray-100');
                document.body.classList.add('bg-red-50');
            }
        }, 100);

        // 联系站长按钮点击事件
        document.getElementById('contact-btn').addEventListener('click', function() {
            const qqNumber = document.getElementById('qq-number');
            qqNumber.classList.toggle('hidden');
            
            // 按钮文字变化
            const btn = document.getElementById('contact-btn');
            if (qqNumber.classList.contains('hidden')) {
                btn.innerHTML = '<i class="fa fa-envelope mr-2"></i>联系站长';
            } else {
                btn.innerHTML = '<i class="fa fa-eye-slash mr-2"></i>隐藏联系方式';
            }
        });
    </script>
</body>
</html>
