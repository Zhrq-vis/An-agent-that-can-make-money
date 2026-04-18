
# Companion.skill

> “这一次，我们不只是做聊天机器人，而是研究 **怎样让 AI 更像一个陪伴的人**。”

![License](https://img.shields.io/badge/License-MIT-yellow)
![Python](https://img.shields.io/badge/Python-3.9+-blue)
![LLM](https://img.shields.io/badge/OpenAI-Compatible-green)
![Architecture](https://img.shields.io/badge/Architecture-Skill--Based-purple)
![Channel](https://img.shields.io/badge/Channel-QQ%20Bot-orange)
![Research](https://img.shields.io/badge/Research-Emotional%20AI-brightgreen)

---

有些 AI 项目不是为了替代人，而是为了 **研究人与 AI 的互动方式**。  
有些系统不是为了“回答问题”，而是为了 **提供情绪价值与陪伴感**。

**Companion.skill** 是一个用于研究 **高自然度 AI 陪伴对话系统** 的实验平台。

系统的目标不是构建一个“机器人”，而是探索：

- AI 如何减少“机器人味”
- AI 如何在长期对话中保持人格一致
- AI 如何通过 Prompt 编排产生更自然的互动
- AI 如何在不训练模型的情况下持续优化体验

---

# 项目定位

Companion.skill 是一个 **基于 Skill 架构的 AI 角色陪伴系统研究平台**。

系统通过以下方式构建：

**Channel Layer → Conversation Orchestrator → Skill Router → Persona Engine → Prompt Lab → LLM Gateway**

并通过用户反馈（如点赞、虚拟红包、继续聊天）作为研究信号，分析不同对话策略的效果。

---

# 系统架构

```
Channel Layer
   └─ QQ Bot / CLI / Web Chat

Gateway Layer
   └─ Message Adapter

Conversation Orchestrator
   ├─ Context Builder
   ├─ Persona Composer
   ├─ Style Controller
   ├─ Reply Planner
   └─ Safety Guard

Skill Layer
   ├─ conversation.reply
   ├─ persona.render
   ├─ memory.read
   ├─ memory.write
   ├─ engagement.plan
   ├─ reward.log
   └─ image.generate

Prompt Lab
   ├─ Prompt Templates
   ├─ Prompt Versions
   └─ Style Packs

Reward Analytics
   ├─ Virtual Tips
   ├─ Satisfaction Score
   └─ Conversation Metrics

LLM Gateway
   └─ OpenAI-Compatible APIs
```

---

# 核心能力

## 1. Persona Engine（角色引擎）

系统支持长期人格一致的 AI 角色，例如：

```yaml
persona_id: luna
display_name: 小栀

tone:
  - 温柔
  - 轻松

speech_style:
  length_pref: short
  emoji_level: low

interests:
  - 奶茶
  - 小蛋糕
  - 电影
```

Persona Engine 负责：

- 角色 Prompt 生成
- 语气控制
- 长期人格一致性

---

## 2. Prompt Lab（Prompt 实验室）

Prompt Lab 用于研究 **不同 Prompt 策略对陪伴感的影响**。

例如：

- 不同语气模板
- 不同回复长度策略
- 不同记忆注入方式
- 不同熟悉度层级

---

## 3. Memory System（记忆系统）

系统支持三层记忆：

| 类型 | 作用 |
|-----|-----|
| Short Memory | 最近对话 |
| Summary Memory | 对话摘要 |
| Preference Memory | 用户偏好 |

---

## 4. Reward System（研究信号）

为了研究用户体验，系统记录以下反馈：

| 类型 | 示例 |
|----|----|
| 虚拟红包 | +5 |
| 点赞 | +2 |
| 继续聊天 | +1 |
| 对话中断 | -1 |

这些数据可用于分析：

- 哪种回复更自然
- 哪种 persona 更受欢迎
- 哪种 Prompt 版本表现更好

---

# 技术特点

本项目刻意 **不使用本地模型训练**：

- 不训练模型
- 不微调模型
- 不在线训练

所有 AI 推理均通过：

**OpenAI Compatible API**

实现策略优化完全依赖：

- Prompt Engineering
- Context Engineering
- Dialogue Policy

---

# 目录结构

```
companion_platform/

app/
  main.py
  orchestrator.py
  llm_gateway.py
  memory.py
  reward.py
  qq_adapter.py

configs/
  personas.yaml
  models.yaml
  prompts/

scripts/
  chat_cli.py

data/
  companion.db

openclaw_skills/
  companion-reply

docker/
  Dockerfile
  docker-compose.yml
```

---

# 安装

创建环境：

```bash
python -m venv .venv
```

Windows

```bash
.venv\Scripts\activate
```

Linux / macOS

```bash
source .venv/bin/activate
```

安装依赖

```bash
pip install -r requirements.txt
```

---

# 本地测试

CLI 聊天

```
python scripts/chat_cli.py
```

示例：

```
User: 今天好累
Bot: 看起来今天被事情拖着走了一整天。
```

---

# 接入 QQ 机器人

1. 创建 QQ 机器人

https://bot.q.qq.com

获取：

```
AppID
AppSecret
```

2. 配置回调地址

```
https://你的域名/qq/events
```

订阅事件

```
C2C_MESSAGE_CREATE
```

---

# OpenClaw 集成（可选）

OpenClaw 可作为 **Skill Runtime**。

安装：

Windows

```
iwr -useb https://openclaw.ai/install.ps1 | iex
```

Linux

```
curl https://openclaw.ai/install.sh | bash
```

将 skill 复制到

```
~/.openclaw/skills/
```

---

# 研究方向

Companion.skill 可用于研究：

- 情绪价值对话系统
- AI 陪伴系统
- Prompt 编排优化
- Persona 一致性
- 对话节奏对体验的影响

---

# License

MIT License
