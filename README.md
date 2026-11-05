# Danbo

一名前端工程师，做中后台系统。更在意的是「一个上百个路由的系统怎样不失控」这类问题，
而不是某个页面怎么写得更好看。

## 正在做的项目

### [atlas-admin](https://github.com/EggDanbo/atlas-admin)

一体化后台管理系统 · Vue 3 + TypeScript + Naive UI

11 个业务域、107 个路由，覆盖人、事、财、物、档的完整链路。
自带本地 mock 引擎，**不连接任何后端**，克隆下来 `pnpm dev` 就能跑通列表、详情、审批、导出。

🔗 [在线体验](https://eggdanbo.github.io/atlas-admin/) · 账号 `demo` / `123456`

三个我自己比较满意的取舍：

| 决策 | 解决什么 | 记录 |
| ---- | -------- | ---- |
| 表格列不写死 | 近百个页面的列定义手写会失控，改为脚本从视图提取字段、由数据生成 | [ADR-0002](https://github.com/EggDanbo/atlas-admin/blob/main/docs/adr/0002-dataformat-driven-columns.md) |
| mock 不是几张静态 JSON | 数据要经得起翻页、搜索、审批流，还要可复现，所以在 Alova 层自研适配器 | [ADR-0001](https://github.com/EggDanbo/atlas-admin/blob/main/docs/adr/0001-local-mock-engine.md) |
| 视觉不散落魔法值 | 换主色只改一个值，明暗两套自动成立 | [ADR-0003](https://github.com/EggDanbo/atlas-admin/blob/main/docs/adr/0003-design-tokens.md) |

## 技术栈

![Vue](https://img.shields.io/badge/Vue_3-42b883?logo=vuedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646cff?logo=vite&logoColor=white)
![Naive UI](https://img.shields.io/badge/Naive_UI-18a058)
![Pinia](https://img.shields.io/badge/Pinia-ffd859?logo=pinia&logoColor=black)
![VXE Table](https://img.shields.io/badge/VXE_Table-4b8bbe)
![ECharts](https://img.shields.io/badge/ECharts-aa344d)
![Vitest](https://img.shields.io/badge/Vitest-729b1b?logo=vitest&logoColor=white)

## 我在意的事

**重复代码是债，不是一个可以靠自觉维护的东西。**
同一个审批弹窗在 32 个页面里各写一遍、只差一个 `biz_class` 参数——这种代码删掉比优化它更值钱。
判断依据是去掉空白后做哈希比对，不是靠翻代码时「好像见过」。

**类型和测试是护栏，不是 KPI。**
`vue-tsc` 全绿、44 个单测、CI 跑完 lint → 类型 → 测试 → 构建，作用是在重构时敢下手。
护栏的意义体现在「改坏了会被拦住」，而不是数字好看。

**文档里写的命令，得在干净环境里真的能执行。**
`pnpm install --frozen-lockfile` 会因为锁文件版本对不上而失败，
`pnpm lint` 会因为你只检查了 `src` 而漏掉根目录——这些只有换一台干净机器才暴露。

## 联系

📮 Spiraldanbo@gmail.com
