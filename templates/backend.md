# 后端服务说明（Go / Java / Node）

<!-- 复制为 CLAUDE.md 或 AGENTS.md，按项目实际情况改。 -->

## 技术栈

- 语言 / 框架：<Go 1.2x + Gin / Spring Boot 3 / Node + NestJS>
- 数据库：<PostgreSQL>，缓存：<Redis>，迁移工具：<golang-migrate / Flyway / Prisma>
- 部署：<Docker Compose>

## 常用命令

- 启动依赖：`docker compose up -d postgres redis`
- 运行：`<go run ./cmd/server>`
- 测试：`<go test ./...>`
- 检查：`<go vet ./... && golangci-lint run>`

## 分层约定

- handler / controller：只做参数校验和响应组装
- service：业务逻辑
- repository / dao：只做数据访问
- 不要跨层调用（handler 直接查数据库是错的）

## 规则

1. **数据库结构变更必须写迁移文件**，不要手改表；迁移要能回滚。
2. **不碰生产配置和密钥**，配置走环境变量；示例写进 `.env.example`。
3. 新接口要写测试，至少覆盖成功路径和一个错误路径。
4. 错误要带上下文返回或记录，不要吞掉；日志不打印密码、token、完整手机号。
5. 涉及金额用整数分或 decimal，不用浮点数。
6. 改公共接口（URL、字段名、返回结构）前先告诉我，可能影响调用方。

## 完成标准

- `go test ./...`（或对应命令）全部通过；
- 说明改动点、是否需要跑迁移、是否影响已有接口。
