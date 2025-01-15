<！doctype html>
<超文本标记语言朗="zh-CN">

<头>
    <元字符集="UTF-8">
    <元姓名="视口" 内容="宽度=设备宽度，初始比例=1.0">
    <标题>计算器</标题>
    <风格>
身体{
            字体系列:Arial,无衬线;
            显示:弯曲;
            justify-content:中心;
            对齐项目:中心;
            高度:100VH;
            边缘:0;
            背景色：#f5f5f5；
            填充:10PX;/* 为小屏幕设备添加内边距 */
        }

    .计算器{
    背景色：#ffffff；
    填料：20px；
    边界半径：10px；
    盒阴影：02px5pxrgba(0，0，0，0.1)；
    width:90%；/*使计算器宽度适应屏幕宽度*/
    最大宽度：360px；/*设置最大宽度，防止在大屏幕上过大*/
    }

    .Display{
    width:100%；/*让显示区域宽度自适应计算器宽度*/
    高度：60px；
    font-size:2EM；
    底边距：20px；
    边框：无；
    边界半径：5px；
    填充：010px；
    文本对齐：右；
    背景色：#f0f0f0；
    }

    .buttons{
    显示：网格；
    网格模板列：重复(4，1fr)；/*保持4列布局*/
    栅距：10px；
    }

    .button{
    字体大小：1.5em；
    边框：无；
    边界半径：5px；
    背景色：#e0e0e0；
    颜色：#333333；
    填充：15px；/*减小按钮内边距，适应小屏幕*/
    光标：指针；
    过渡：背景色0.3s轻松；
    }

    .button：悬停{
    背景色：#d0d0d0；
    }

    .operator{
    背景色：#007aff；
    颜色：#ffffff；
    }

    .operator：悬停{
    背景色：#0062cc；
    }

    .等于{
    背景色：#00cc66；
    网格柱：跨2；
    颜色：#ffffff；
    }

    .equal：悬停{
    背景色：#00a34d；
    }

       .clear {
            background-color: #ff4d4d;
            color: #ffffff;
            grid-row: 1;
            grid-column: 1;
        }

       .clear:hover {
            background-color: #e03e3e;
        }

       .delete {
            background-color: #ff9800;
            color: #ffffff;
            grid-row: 1;
            grid-column: 2;
        }

       .delete:hover {
            background-color: #e68a00;
        }
    </style>
</head>

<body>
    <div class="calculator">
        <input type="text" id="display" class="display" readonly>
        <div class="buttons">
            <button class="button clear" onclick="clearDisplay()">C</button>
            <button class="button delete" onclick="deleteValue()">←</button>
            <button class="button" onclick="appendValue('7')">7</button>
            <button class="button operator" onclick="appendValue('/')">÷</button>
            <button class="button" onclick="appendValue('4')">4</button>
            <button class="button" onclick="appendValue('5')">5</button>
            <button class="button" onclick="appendValue('6')">6</button>
            <button class="button operator" onclick="appendValue('*')">×</button>
            <button class="button" onclick="appendValue('1')">1</button>
            <button class="button" onclick="appendValue('2')">2</button>
            <button class="button" onclick="appendValue('3')">3</button>
            <button class="button operator" onclick="appendValue('-')">-</button>
            <button class="button" onclick="appendValue('0')">0</button>
            <button class="button" onclick="appendValue('.')">.</button>
            <button class="button equal" onclick="calculate()">=</button>
            <button class="button operator" onclick="appendValue('+')">+</button>
        </div>
    </div>
    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }

        function calculate() {
            try {
                let result = eval(document.getElementById('display').value);
                document.getElementById('display').value = result;
            } catch (error) {
                document.getElementById('display').value = '错误';
            }
        }

        function deleteValue() {
            let currentValue = document.getElementById('display').value;
            document.getElementById('display').value = currentValue.slice(0, -1);
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }
    </script>
</body>

</html>
