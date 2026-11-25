# React 开发规范

## 组件

- 一律使用函数组件 + Hooks，不新增 class 组件
- 组件文件使用 PascalCase 命名，一个文件只导出一个主组件
- 组件超过约 150 行时考虑拆分；优先拆分子组件，而不是堆 useMemo
- props 使用 TypeScript interface 显式定义，命名为 `组件名Props`

## Hooks

- 遵守 Hooks 规则：只在顶层调用，不在条件、循环、嵌套函数中调用
- `useEffect` 依赖数组必须完整、如实；禁止用 eslint-disable 压制 exhaustive-deps 警告
- 能在渲染期计算的值不用 state + effect 同步；派生状态优先在渲染中直接计算
- 自定义 Hook 以 `use` 开头，只在逻辑确实被两处以上复用时才抽取

## 状态管理

- 局部状态用 `useState`；跨层级共享优先 `useContext`；确有需要再引入状态库，并跟随项目已有选型
- 不把服务端数据塞进全局状态库，服务端状态用项目已有的数据请求方案管理

## 性能

- 不预防性优化：没有测量依据时不加 `useMemo` / `useCallback` / `React.memo`
- 列表渲染必须提供稳定 `key`，禁止使用数组下标作为 key（静态列表除外）
- 大列表考虑虚拟化；路由级组件使用懒加载

## 样式

- 跟随项目已有的样式方案（CSS Modules / Tailwind / styled-components），不混用多套
- 不滥用内联 style；动态样式值除外
