# npm-collections

TypeScript monorepo with pnpm workspace.

## 项目结构

```
npm-collections/
├── packages/         # 共享包
│   ├── core/         # 核心工具包
│   └── shared/       # 共享类型和工具
├── apps/             # 加密文件(packages/)
│   └── example/      
├── apps-code/        # 解密文件
│   └── example/      
├── pnpm-workspace.yaml
├── package.json
└── tsconfig.base.json
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

### @npm-collections/core

核心工具包，包含通用工具函数。

### @npm-collections/shared

共享类型和工具，供其他包使用。

## License

ISC
