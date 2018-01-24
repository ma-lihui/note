# SVG动画
## 结合CSS 实现动画
### Loading动画
  <svg width="600" height="200">
    <style>
    <style>
        .dot1{ 
            animation: slide1 2s infinite;
         } 
         .dot2{ 
            animation: slide2 2s infinite;
         } 
        @keyframes slide1 { 
            0%, 100% { 
                transform: translateX(0px); 
            } 
            50% { 
                transform: translateX(100px); 
            }
        }
        @keyframes slide2 { 
            0%, 100% { 
                transform: translateX(0px); 
            } 
            50% { 
                transform: translateX(-100px); 
            }
        }
    </style>
    </style>
    
    <defs>
      <filter id="goo">
        <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
       <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="goo" />
      </filter>
    </defs>
    <g filter="url(#goo)">
      <circle class="dot1" cx="50" cy="50" r="25" fill="#f1c40f" />
      <circle class="dot2" cx="150" cy="50" r="25" fill="#ff5050" />
    </g>
  </svg>
  
```
  <svg width="600" height="200">
    <style>
    <style>
        .dot1{ 
            animation: slide1 2s infinite;
         } 
         .dot2{ 
            animation: slide2 2s infinite;
         } 
        @keyframes slide1 { 
            0%, 100% { 
                transform: translateX(0px); 
            } 
            50% { 
                transform: translateX(100px); 
            }
        }
        @keyframes slide2 { 
            0%, 100% { 
                transform: translateX(0px); 
            } 
            50% { 
                transform: translateX(-100px); 
            }
        }
    </style>
    </style>
    
    <defs>
      <filter id="goo">
        <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
       <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="goo" />
      </filter>
    </defs>
    <g filter="url(#goo)">
      <circle class="dot1" cx="50" cy="50" r="25" fill="#f1c40f" />
      <circle class="dot2" cx="150" cy="50" r="25" fill="#ff5050" />
    </g>
  </svg>

```
### 环形进度条动画
  <svg width="400" height="300">
      <style>
      #progress{
        stroke-dasharray:628;
        stroke-dashoffset: 628;
        animation: dash 3s infinite;
        transform: rotate(-90deg);
        transform-origin: 50%;
      }
     @keyframes dash{
        to{
          stroke-dashoffset: 100;
        }
      }
     </style>
     <linearGradient id="gradient" x1="0%" y1="0%" x2="0%" y2="100%">>
    		<stop offset="0%" stop-color="#ff60c9"/>
    		<stop offset="100%" stop-color="#39c0ff"/>
      </linearGradient>
      <circle r="100" cx="150" cy="150" fill="transparent" stroke="#ccc" stroke-width="15" stroke-linecap="round" opacity="0.2"/>
      <circle id="progress" r="100" cx="150" cy="150" fill="transparent" stroke="url(#gradient)" stroke-width="15" stroke-linecap="round"/>
  </svg>
  
```svg
  <svg width="400" height="300">
      <style>
      #progress{
        stroke-dasharray:628;
        stroke-dashoffset: 628;
        animation: dash 3s infinite
      }
     @keyframes dash{
        to{
          stroke-dashoffset: 150;
        }
      }
    </style>
      <circle r="100" cx="150" cy="150" fill="transparent" stroke="#ccc" stroke-width="15" stroke-linecap="round" opacity="0.2"/>
      <circle id="progress" r="100" cx="150" cy="150" fill="transparent" stroke="#39c0ff" stroke-width="15" stroke-linecap="round"/>
  </svg>
  ```
## 通过SMIL(Synchronized Multimedia Integration Language) 实现动画

 ### `<animate>` 定义属性动画

<svg width="500" height="100">
  <circle id="orange-circle" r="30" cx="50" cy="50" fill="orange" />
  <animate 
           xlink:href="#orange-circle"
           attributeName="cx"
           from="50"
           to="450" 
           dur="1s"
           begin="click"
           repeatCount="2" 
           fill="freeze" />
</svg>

```svg
<svg width="500" height="100">
  <circle id="orange-circle" r="30" cx="50" cy="50" fill="orange" />
  <animate 
           xlink:href="#orange-circle"
           attributeName="cx"
           from="50"
           to="450" 
           dur="1s"
           begin="click"
           repeatCount="2" 
           fill="freeze" />
</svg>
```
* `xlink:href`  动画目标
* `attributeName` 属性名
* `from` 开始值
* `to` 结束值。
* `dur` duration 持续的时间
* `begin`开始动画的触发条件。可以是events ,如focusin, activate, click, mouseover 等。也可以是时间，如 `begin="2s"` ，表示2s 后执行。甚至可以组合使用 `begin="click + 2s"`
* `repeatCount` 动画重复次数
* `fill` 表示动画完成后是否回到初始状态。  
    * remove  默认值，回到初始状态
    * freeze 停留在动画结束时的状态
    
    
### `<animateMotion>  `定义路径动画
    
<svg viewBox="0 0 3387 1270">
	<style>
    .planePath {
      stroke: #D9DADA;
      stroke-width: .5%;
      stroke-dasharray: 1% 2%;
      stroke-linecap: round;
      fill: none;
    }
  </style>
  
  <path id="planePath" class="planePath" d="M-226 626c439,4 636,-213 934,-225 755,-31 602,769 1334,658 562,-86 668,-698 266,-908 -401,-210 -893,189 -632,630 260,441 747,121 1051,91 360,-36 889,179 889,179"  />
  <g id="plane">
    <polygon fill="#D9DADA" points="-141,-10 199,0 -198,-72 -188,-61 -171,-57 -184,-57 " />
    <polygon fill="#C5C6C6" points="199,0 -141,-10 -163,63 -123,9 " />
    <polygon fill="#AEAFB0" points="-95,39 -113,32 -123,9 -163,63 -105,53 -108,45 -87,48 -90,45 -103,41 -94,41 " />
    <path fill="#9D9E9E" d="M-87 48l-21 -3 3 8 19 -4 -1 -1zm-26 -16l18 7 -2 -1 32 -7 -29 1 11 -4 -24 -1 -16 -18 10 23zm10 9l13 4 -4 -4 -9 0z" />
    <polygon fill="#D9DADA" points="-83,28 -94,32 -65,31 -97,38 -86,49 -67,70 199,0 -123,9 -107,27 " />
  </g>
  
  <animateMotion xlink:href="#plane" dur="5s" repeatCount="indefinite" rotate="auto">
    <mpath xlink:href="#planePath" />
  </animateMotion> 
</svg>

```svg
<svg viewBox="0 0 3387 1270">
	<style>
    .planePath {
      stroke: #D9DADA;
      stroke-width: .5%;
      stroke-dasharray: 1% 2%;
      stroke-linecap: round;
      fill: none;
    }
  </style>
  
  <path id="planePath" class="planePath" d="M-226 626c439,4 636,-213 934,-225 755,-31 602,769 1334,658 562,-86 668,-698 266,-908 -401,-210 -893,189 -632,630 260,441 747,121 1051,91 360,-36 889,179 889,179"  />
  <g id="plane">
    <polygon fill="#D9DADA" points="-141,-10 199,0 -198,-72 -188,-61 -171,-57 -184,-57 " />
    <polygon fill="#C5C6C6" points="199,0 -141,-10 -163,63 -123,9 " />
    <polygon fill="#AEAFB0" points="-95,39 -113,32 -123,9 -163,63 -105,53 -108,45 -87,48 -90,45 -103,41 -94,41 " />
    <path fill="#9D9E9E" d="M-87 48l-21 -3 3 8 19 -4 -1 -1zm-26 -16l18 7 -2 -1 32 -7 -29 1 11 -4 -24 -1 -16 -18 10 23zm10 9l13 4 -4 -4 -9 0z" />
    <polygon fill="#D9DADA" points="-83,28 -94,32 -65,31 -97,38 -86,49 -67,70 199,0 -123,9 -107,27 " />
  </g>
  
  <animateMotion xlink:href="#plane" dur="5s" repeatCount="indefinite" rotate="auto">
    <mpath xlink:href="#planePath" />
  </animateMotion> 
</svg>
```

路径动画的另一种写法
```
  <animateMotion 
          xlink:href="#plane"
          attributeName="d"
          dur="5s"
          repeatCount="indefinite"
          rotate="auto"
          path="M-226 626c439,4 636,-213 934,-225 755,-31 602,769 1334,658 562,-86 668,-698 266,-908 -401,-210 -893,189 -632,630 260,441 747,121 1051,91 360,-36 889,179 889,179"
          />
 ```

