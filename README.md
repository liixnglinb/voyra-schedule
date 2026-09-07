# voyra-schedule · 日程中心

> Voyra 个人网站（https://lxlrwxs.top）的「日程中心」模块源码。
> 本仓库为唯一源码来源，push 后通过 GitHub Actions 自动同步至 Voyra 主仓库并触发部署。

## 功能

- **课程表（ClassSchedule）**：大学课表，以「两节连堂」为节次单位（1-2 / 3-4 / 5-6 / 7-8 / 晚自习1 / 晚自习2）；周次自动定位；老师职称完整显示（如「龙承星副教授」）；教室识别；课程明细默认折叠
- **Excel / xls 导入**：支持教务系统网格课表（表头首列空、第 X 大节(01,02)、格内周次混写 `2-17([周])[01-02节]`、逗号隔周 `3,5,7,9([周])`、单周/双周自动识别）
- **文本识别导入**：粘贴文本自动识别课程
- **时间自定义**：每节课时间、晚自习时间可调；iOS 风格滚轮时间选择器
- **日历日程（Planner）**：月历视图 + 2026 法定节假日/调休植入；自定义日程（开学/放假/考试/活动）；本地存储
- **今日概览**：日期 / 今日课程 / 今日日程自动汇总

## 技术栈

- React 18 · Vite 5 · HashRouter
- lucide-react 图标
- xlsx（Excel 解析）
- localStorage 本地存储（登录用户按用户隔离）

## 目录说明

```
src/pages/
├── ScheduleHub.jsx     # 日程中心入口：课程表/日历日程模式切换 + 今日概览
├── ClassSchedule.jsx   # 课程表：节次块 / 周次 / 导入 / 时间设置
└── Planner.jsx         # 日历日程：月历 / 节假日 / 自定义事项
```

> 依赖主仓库共享模块（`src/lib/auth`、`src/components/AuthGate`、`src/components/DateTimePicker`），需在 Voyra 主仓库环境运行。

## 开发与同步流程

1. 修改 `src/pages/` 下文件（建议在 Voyra 主仓库本地副本中开发调试，依赖完整）
2. 将改动复制回本仓库对应文件
3. `git push` → GitHub Actions 自动同步到 [Voyra](https://github.com/liixnglinb/Voyra) 主仓库 → Cloudflare Pages 自动部署

## 搜索关键词

课表、日程、大学课表、课程表、日历、教务系统、timetable、schedule、planner、calendar、react
