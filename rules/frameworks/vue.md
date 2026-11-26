# Vue 开发规范

## 组件

- 一律使用 Composition API + `<script setup>`；已有 Options API 的老项目跟随现状，不擅自重写
- 组件文件使用 PascalCase 命名，一个文件只导出一个组件
- props 使用 `defineProps<T>()` 类型化声明；事件使用 `defineEmits<T>()` 显式声明，不使用字符串数组兜底
- 组件超过约 200 行时考虑拆分子组件或抽取 composable

## 响应式

- 基础类型用 `ref`，对象优先 `ref` 而非 `reactive`（避免解构丢失响应性的问题）；项目已有约定则跟随
- 派生数据用 `computed`，不用 `watch` + 手动赋值模拟
- `watch` 必须明确监听源与必要性；深度监听（`deep: true`）须说明理由
- 跨组件共享逻辑抽取为 `use` 开头的 composable，只在确实复用时才抽取

## 模板

- `v-if` 与 `v-for` 不写同一元素；先用计算属性过滤列表
- 列表渲染使用稳定 `:key`，禁止用数组下标（静态列表除外）
- 模板里不写复杂表达式，超过一行的逻辑移入计算属性或方法

## 状态与样式

- 跨层级状态用 Pinia，store 按业务域拆分；不把服务端缓存数据无脑塞 store
- 样式默认 `<style scoped>`；全局样式集中管理，不滥用 `:deep()`
- 跟随项目已有的样式方案（Tailwind / CSS 变量 / UI 库主题），不混用多套
