# npm-collections

TypeScript monorepo with pnpm workspace.

## 项目结构

```
npm-collections/
├── packages/                   # 库源码
│   ├── first-registry/         # 第一个 npm 库
│   └── second-registry/        # 第二个 npm 库
├── apps/                       # 加密库(packages/)
│   ├── first-registry/         # 第一个加密 npm 库
│   └── second-registry/        # 第二个加密 npm 库
├── apps-code/                  # 库源码
│   ├── first-registry/         # 第一个 npm 库
│   └── second-registry/        # 第二个 npm 库
├── pnpm-workspace.yaml
├── package.json
└── tsconfig.base.json
└── tsconfig.json
```

## 技术栈

- **包管理**: pnpm
- **语言**: TypeScript
- **架构**: Monorepo

## 使用说明

对所有发布到 npm 仓库的库源码进行统一管理（apps）

## 添加新包

### 创建新包

1. 在 `apps/` 目录下创建新项目
2. 创建 `package.json` 并设置正确的内容

### 在包中使用其他包

在 `package.json` 中添加依赖：

```json
{
  "dependencies": {
    "@npm-collections/core": "workspace:*"
  }
}
```


## 包说明

### aes-cbc-helper

提供浏览器端对称加密功能的一个库。

### vite-plugin-config-helper

vite 插件, 能快速集成基于 element-plus 的后台管理系统的 。

### vite-plugin-env-helper

vite 插件，能够提供 typescript 的类型支持和复杂对象变量的支持。

### vite-plugin-scan-routes

vite 插件，能够提供 typescript 的类型支持和复杂对象变量的支持。

### validator-cnid

验证给定字符是否合法。实现了两个功能: isValidCNID 和 isFemale 。
#### 技术要点
* 字符截取函数 substring（substr已废弃） slice，这两个的区别就是 slice 可接收负数，而 substring 是会把负数转换成 0 处理，且它总是会把两个参数中最小的值作为起点。
* Date 构造函数接收参数时， year（0-99）会被解释为 1900 年开始的第 year 年、 month 范围为 0-11， day 范围为 1-31 等等。接收参数不合法时，getDate会返回上一月的最后一天，所以一般用 new Date(2025,11,0) 获取11月的最大天数。

## License

ISC
