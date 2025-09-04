# 图变手办 (Figmorph)

一个基于 OpenAI 接口 & Google Gemini 接口的 AstrBot 插件，可将任意图片一键“手办化”，生成高质量的二次元手办风格图像

## 🔧 功能特性

- **一键生成**：发送“手办化”指令即可完成转换，无需额外操作。
- **多种输入方式**：支持发送图片、回复图片、或 `@用户` 获取头像进行处理。
- **双风格支持**：
  - `deluxe_box`：生成带商业包装盒的精美手办图。
  - `classic`：生成桌面场景中的真实感手办图。
- **GIF 自动处理**：自动提取 GIF 第一帧，无需手动转换。
- **提示词可调**：所有生成提示词（Prompt）均可在配置文件中自定义，支持深度微调。
- **多 Key 高可用**：支持配置多个 API Key，自动切换以应对失效或速率限制。
- **双接口支持**：同时支持 Gemini API 和 OpenAI API，用户可根据需要选择。
  - **Gemini API**：支持图片输入，可直接将用户图片转换为手办风格
  - **OpenAI API**：支持图片输入（gpt-image-1）和纯文字生成（dall-e-3）
- **自定义模型支持**: 支持用户自定义模型，以便使用自己的服务

## ⚙️ 安装与配置

### 安装步骤

1. 下载插件压缩包并解压。
2. 将 `astrbot_plugin_figmorph` 文件夹放入 `astrbot/plugins` 目录。
3. 重启 AstrBot。

### 配置项说明

在 AstrBot 管理面板中进入 `插件管理` → `图变手办` 进行设置：

| 配置项                | 类型     | 描述                                                                                                                              |
|-----------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------|
| `api_type`            | 下拉菜单 | **必填**：选择使用的API接口类型，`gemini` 或 `openai`                                                                             |
| `gemini_api_keys`     | 列表     | **必填**（当选择gemini时）：填写一个或多个 Google Gemini API 密钥。获取地址：[Google AI Studio](https://aistudio.google.com/) |
| `openai_api_keys`     | 列表     | **必填**（当选择openai时）：填写一个或多个 OpenAI API 密钥。获取地址：[OpenAI Platform](https://platform.openai.com/)        |
| `figurine_style`      | 下拉菜单 | 默认生成风格：`deluxe_box` 或 `classic`                                                                                           |
| `save_image`          | 开关     | 是否将生成图像保存至插件的 `data` 目录                                                                                             |
| `gemini_api_base_url` | 字符串   | （可选）自定义 Gemini API 地址，适用于代理场景                                                                                     |
| `openai_api_base_url` | 字符串   | （可选）自定义 OpenAI API 地址，适用于代理场景                                                                                     |
| `gemini_model_name`   | 字符串   | （可选）指定使用的 Gemini 模型，留空则使用默认：`gemini-2.0-flash-preview-image-generation`                                       |
| `openai_model_name`   | 字符串   | （可选）指定使用的 OpenAI 模型，留空则使用默认：`dall-e-3`                                                                         |
| `prompts`             | 对象     | （高级）自定义 `deluxe_box` 与 `classic` 风格的提示词，控制图像风格与细节                                                         |

## 🚀 使用方法

### Gemini API（支持图片输入）
- 发送 `手办化` 并附图。
- 回复一张图片并发送 `手办化`。
- 使用 `手办化 @某人` 将对方头像手办化。

### OpenAI API（支持图片输入和文字描述）
- **图片输入**：发送 `手办化` 并附图（使用 gpt-image-1 模型）
- **文字描述**：发送 `手办化 描述内容`（例如：手办化 一只可爱的小猫，使用 dall-e-3 模型）
- 支持两种生成方式，根据输入自动选择

## 🙏 致谢

插件二改自作者  [**zgojin**](https://github.com/zgojin/) 的插件 [**astrbot_plugin_figurine_workshop**](https://github.com/zgojin/astrbot_plugin_figurine_workshop)
在此表示诚挚的感谢！
