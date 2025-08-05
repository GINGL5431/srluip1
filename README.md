<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>制作人介绍</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    
    <!-- 配置Tailwind自定义颜色 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        gradient1: '#8B5CF6',
                        gradient2: '#EC4899',
                        gradient3: '#3B82F6',
                        gradient4: '#10B981',
                        gradient5: '#F59E0B',
                    },
                }
            }
        }
    </script>
    
    <style type="text/tailwindcss">
        @layer utilities {
            /* 渐变文本工具类 */
            .text-gradient-1 {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(135deg, #8B5CF6, #EC4899);
            }
            .text-gradient-2 {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(135deg, #3B82F6, #10B981);
            }
            .text-gradient-3 {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(135deg, #F59E0B, #EF4444);
            }
            .text-gradient-4 {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(135deg, #6366F1, #06B6D4);
            }
            .text-gradient-5 {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(135deg, #EC4899, #8B5CF6);
            }
            
            /* 卡片悬停效果 */
            .producer-card {
                transition: transform 0.3s ease, box-shadow 0.3s ease;
            }
            .producer-card:hover {
                transform: translateY(-5px);
                box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            }
            
            /* 滚动提示动画 */
            @keyframes bounce {
                0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
                40% {transform: translateY(-10px);}
                60% {transform: translateY(-5px);}
            }
            .scroll-indicator {
                animation: bounce 2s infinite;
            }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-gray-50 to-gray-100 font-sans">
    <div class="container mx-auto px-4 py-8 max-w-4xl">
        <!-- 页面标题 -->
        <header class="text-center mb-12 mt-8">
            <h1 class="text-[clamp(1.8rem,5vw,3rem)] font-bold text-gradient-1 mb-4">
                关于我们的团队
            </h1>
            <p class="text-gray-600 text-lg">
                制作人团队介绍（上下滑动浏览）
            </p>
            
            <!-- 滚动提示 -->
            <div class="mt-8 hidden md:block">
                <p class="text-gray-500 mb-2 text-sm">向下滑动浏览</p>
                <i class="fa fa-chevron-down text-gray-400 scroll-indicator"></i>
            </div>
        </header>
        
        <!-- 制作人卡片容器（上下排列） -->
        <div class="space-y-8 pb-20">
            <!-- 制作人 1 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-1 mb-3">模糊的记忆AI是无解命题</h2>
                <p class="text-gray-700 mb-4">项目总监</p>
                <p class="text-gradient-1/90 leading-relaxed">
                    拥有6年触发器基础，本项目发起人之一。
                </p>
            </div>
            
            <!-- 制作人 2 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-2 mb-3">巫马蜜桔</h2>
                <p class="text-gray-700 mb-4">项目副总监</p>
                <p class="text-gradient-2/90 leading-relaxed">
                    建筑，触发器，调试，本项目发起人之一。
                </p>
            </div>
            
            <!-- 制作人 3 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-3 mb-3">难言</h2>
                <p class="text-gray-700 mb-4">思想设计</p>
                <p class="text-gradient-3/90 leading-relaxed">
                    地图思想功能设计，材料设计。
                </p>
            </div>
            
            <!-- 制作人 4 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-4 mb-3">乌萨奇</h2>
                <p class="text-gray-700 mb-4">资金股东</p>
                <p class="text-gradient-4/90 leading-relaxed">
                    提供地图资金内容，赞助。
                </p>
            </div>
            
            <!-- 制作人 5 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-5 mb-3">小染子</h2>
                <p class="text-gray-700 mb-4">反馈客服</p>
                <p class="text-gradient-5/90 leading-relaxed">
                    地图客服，收集地图的任何bug，问题等。
                </p>
            </div>
            
            <!-- 制作人 6 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-1 mb-3">赵伟</h2>
                <p class="text-gray-700 mb-4">前端工程师</p>
                <p class="text-gradient-1/90 leading-relaxed">
                    资深前端开发工程师，擅长构建直观易用的用户界面。负责项目可视化展示与交互设计，让复杂的AI技术以友好的方式呈现。
                </p>
            </div>
            
            <!-- 制作人 7 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-2 mb-3">空白</h2>
                <p class="text-gray-700 mb-4">思想设计</p>
                <p class="text-gradient-2/90 leading-relaxed">
                    思想地图功能设计，提出有效意见。
                </p>
            </div>
            
            <!-- 制作人 8 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-3 mb-3">L</h2>
                <p class="text-gray-700 mb-4">后端玩家管理</p>
                <p class="text-gradient-3/90 leading-relaxed">
                    后端系统玩家管理，负责交流群管理等。
                </p>
            </div>
            
            <!-- 制作人 9 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-4 mb-3">史</h2>
                <p class="text-gray-700 mb-4">技术顾问</p>
                <p class="text-gradient-4/90 leading-relaxed">
                    负责图片转为2d像素。
                </p>
            </div>
            
            <!-- 制作人 10 -->
            <div class="producer-card bg-white rounded-2xl p-6 md:p-8 shadow-lg">
                <h2 class="text-2xl md:text-3xl font-bold text-gradient-5 mb-3">0312</h2>
                <p class="text-gray-700 mb-4">玩家指导</p>
                <p class="text-gradient-5/90 leading-relaxed">
                    指导玩家游戏内容，兼玩家管理。
                </p>
            </div>
        </div>
        
        <!-- 回到顶部按钮 -->
        <button id="backToTop" class="fixed bottom-8 right-8 bg-gradient-to-r from-gradient1 to-gradient2 text-white w-12 h-12 rounded-full shadow-lg flex items-center justify-center opacity-0 invisible transition-all duration-300 hover:scale-110">
            <i class="fa fa-chevron-up"></i>
        </button>
    </div>

    <script>
        // 回到顶部按钮功能
        const backToTopBtn = document.getElementById('backToTop');
        
        // 监听滚动事件
        window.addEventListener('scroll', () => {
            // 当滚动超过300px时显示回到顶部按钮
            if (window.scrollY > 300) {
                backToTopBtn.classList.remove('opacity-0', 'invisible');
                backToTopBtn.classList.add('opacity-100', 'visible');
            } else {
                backToTopBtn.classList.remove('opacity-100', 'visible');
                backToTopBtn.classList.add('opacity-0', 'invisible');
            }
        });
        
        // 回到顶部点击事件
        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // 平滑滚动支持
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
    
