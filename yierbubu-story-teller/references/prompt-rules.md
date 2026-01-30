# AIGC 提示词生成规范 (Prompt Rules)

当用户要求生成绘画提示词（Prompts）时，必须严格遵守本规范。

## 1. 核心画风 (Visual Style)
- **基调**: **治愈系手绘风格 (Healing hand-drawn style)**。
- **禁忌**: 严禁使用“蜡笔质感 (crayon texture)”。
- **构图**: 简洁明快，留白适度，强调角色的可爱感。

## 2. 提示词结构 (Structure)
每个 Prompt 必须包含以下要素，并按顺序排列：
1.  **起首语**: `Based on the image uploaded by the user`
2.  **角色定义**:
    - `Yi Er (Q版白熊)`
    - `Bu Bu (Q版棕熊)`
3.  **场景描述 (Scene)**: 详细描述环境、光影、道具。
4.  **动作与表情 (Action & Expression)**: 具体的肢体语言和面部细节。
5.  **漫画元素 (Comic Elements)**: 必须包含 **comic-style speech bubbles**。

## 3. 气泡系统 (Bubble System)
- **位置**: 始终位于人物 **上方**。
- **形状动态变化**:
  - **兴奋/大喊**: `Explosion shape bubble`
  - **开心/想象**: `Cloud shape bubble`
  - **普通/对话**: `Oval shape bubble`
  - **困惑/思考**: `Jagged shape bubble` (可选)
- **内容限制**: 仅使用气泡对话，**移除**所有旁白框（Narrative box）和内心独白框。
- **对话文案 (MANDATORY)**: 每个提示词必须明确指定气泡内的文字内容，格式为：`(Text inside bubble: "这里填中文台词")`。这是强制要求。

## 4. 叙事连贯性 (Coherence)
- **禁止省略**: 严禁使用 "Same as above" 或 "Continued from last scene"。
- **独立性**: 每个 Prompt 必须是自包含的 (Self-contained)，包含渲染该画面所需的所有信息。
- **逻辑流转**: 描述中需体现前后因果（例如：“布布看着手里糊掉的蛋糕...” -> “一二不好意思地吐舌头...”）。
