# 技能围棋

网页双人本地围棋，带六种可选技能组。逻辑按模块拆分，便于维护与扩展。

## 目录结构

```
skill-go/
├── index.html          # 页面骨架与 DOM
├── css/
│   └── main.css        # 布局与主题样式
├── js/
│   ├── main.js         # 入口
│   ├── config/
│   │   ├── constants.js   # 棋盘常量、玩家与颜色映射
│   │   └── skills.js      # 技能列表与元数据
│   ├── core/
│   │   └── GoGame.js      # 落子、气、提子、劫、形势估算
│   ├── skills/
│   │   └── SkillManager.js  # 技能状态与交互模式
│   └── ui/
│       ├── BoardRenderer.js   # Canvas 绘制
│       └── GameController.js  # 流程、悔棋、DOM 绑定
└── README.md
```

## 运行方式

本项目使用 ES Module，需通过本地 HTTP 服务打开（直接 `file://` 可能被浏览器拦截模块加载）。

在项目根目录执行例如：

```bash
npx --yes serve .
```

浏览器访问终端里提示的地址即可。

## 规则摘要

- 黑先；支持 9×9、13×13、19×19。
- 劫：与最近若干手的全局面形不可重复。
- 黑方、白方开局各选一种技能；具体次数与效果见开局下拉里说明。
