# no-bullshit / plain-language

一个让 AI 说人话的全局 Agent Skill。

适用于任何自然语言输出:回答问题、解释概念、debug、code review、架构设计、科研讨论、论文分析、工作汇报、周报、会议、邮件、IM、文档写作、日常交流。不限领域。

## 它治什么病

1. **空话**。AI 爱写"该方案具有较好的灵活性和扩展性"。判断标准:一句话几乎不改就能放进 50 个不相关的回答里,它就是废话。
2. **翻译腔**。英语思维的中文:reconcile 硬译成"对账"、"昂贵的开销"、"对该模块进行了集成"。词是中文的,脑子是英文的。
3. **答案被埋**。重点藏在第三段中间,前面是铺垫,后面是总结。看的人要自己挖。

## 核心机制

8 条 Core Rules,按优先级排序:

1. **Answer first** — 先回答用户真正问的问题
2. **Concrete before abstract** — 先说具体发生了什么,再引入概念
3. **Every abstraction must cash out** — 抽象词必须能落到具体对象、行为或例子
4. **Minimum necessary complexity** — 问题可以复杂,表达不额外加复杂度
5. **Information over ceremony** — 删掉不损失信息的句子就删
6. **Preserve technical precision** — 术语照常用,不为口语化牺牲准确性
7. **Match the requested register** — 文体随场景,但任何文体都必须有信息量
8. **Write Chinese as Chinese** — 不要在脑内先写英文再翻译成中文

前 7 条中英双语都适用,第 8 条针对中文输出。

## 安装

```bash
# 装到用户级 skill 目录
cp -r skills/plain-language ~/.agents/skills/

# (ZCode)全局自动生效:把 AGENTS.md 的内容放进 ~/.zcode/AGENTS.md
cat AGENTS.md >> ~/.zcode/AGENTS.md
```

skill 只有 description 常驻上下文,正文不保证每个会话加载。上面的 AGENTS.md 片段是全局入口:每个会话注入一段短指针和最高原则,细则留在 skill 正文里,避免两份内容重复维护。

## 一个例子

改前:

> 该方案可以降低用户侧的认知负担。

改后:

> 用户不用再记第二个密码。

完整规则和 12 组对比示例见 [skills/plain-language/SKILL.md](skills/plain-language/SKILL.md)。

## 致谢

"每轮报进度""列表不超过 5 项""首末行测试"等机制参考了 [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)。

## 许可

[MIT](LICENSE)
