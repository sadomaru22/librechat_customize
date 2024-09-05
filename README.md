<p align="center">
  <a href="https://librechat.ai">
    <img src="client/public/assets/logo.svg" height="256">
  </a>
  <h1 align="center">
    <a href="https://librechat.ai">LibreChat</a>
  </h1>
</p>

<p align="center">
  <a href="https://discord.librechat.ai"> 
    <img
      src="https://img.shields.io/discord/1086345563026489514?label=&logo=discord&style=for-the-badge&logoWidth=20&logoColor=white&labelColor=000000&color=blueviolet">
  </a>
  <a href="https://www.youtube.com/@LibreChat"> 
    <img
      src="https://img.shields.io/badge/YOUTUBE-red.svg?style=for-the-badge&logo=youtube&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
  <a href="https://docs.librechat.ai"> 
    <img
      src="https://img.shields.io/badge/DOCS-blue.svg?style=for-the-badge&logo=read-the-docs&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
  <a aria-label="Sponsors" href="https://github.com/sponsors/danny-avila">
    <img
      src="https://img.shields.io/badge/SPONSORS-brightgreen.svg?style=for-the-badge&logo=github-sponsors&logoColor=white&labelColor=000000&logoWidth=20">
  </a>
</p>

<p align="center">
<a href="https://railway.app/template/b5k2mn?referralCode=HI9hWz">
  <img src="https://railway.app/button.svg" alt="Deploy on Railway" height="30">
</a>
<a href="https://zeabur.com/templates/0X2ZY8">
  <img src="https://zeabur.com/button.svg" alt="Deploy on Zeabur" height="30"/>
</a>
<a href="https://template.cloud.sealos.io/deploy?templateName=librechat">
  <img src="https://raw.githubusercontent.com/labring-actions/templates/main/Deploy-on-Sealos.svg" alt="Deploy on Sealos" height="30">
</a>
</p>

# 📃 Features

- 🖥️ UI matching ChatGPT, including Dark mode, Streaming, and latest updates
- 🤖 AI model selection:
  - OpenAI, Azure OpenAI, BingAI, ChatGPT, Google Vertex AI, Anthropic (Claude), Plugins, Assistants API (including Azure Assistants)
- ✅ Compatible across both **[Remote & Local AI services](https://www.librechat.ai/docs/configuration/librechat_yaml/ai_endpoints):**
  - groq, Ollama, Cohere, Mistral AI, Apple MLX, koboldcpp, OpenRouter, together.ai, Perplexity, ShuttleAI, and more
- 🪄 Generative UI with [Code Artifacts](https://youtu.be/GfTj7O4gmd0?si=WJbdnemZpJzBrJo3)
  - Create React, HTML code, and Mermaid diagrams right in chat
- 💾 Create, Save, & Share Custom Presets
- 🔀 Switch between AI Endpoints and Presets, mid-chat
- 🔄 Edit, Resubmit, and Continue Messages with Conversation branching
- 🌿 Fork Messages & Conversations for Advanced Context control
- 💬 Multimodal Chat:
  - Upload and analyze images with Claude 3, GPT-4 (including `gpt-4o` and `gpt-4o-mini`), and Gemini Vision 📸
  - Chat with Files using Custom Endpoints, OpenAI, Azure, Anthropic, & Google. 🗃️
  - Advanced Agents with Files, Code Interpreter, Tools, and API Actions 🔦
    - Available through the [OpenAI Assistants API](https://platform.openai.com/docs/assistants/overview) 🌤️
    - Non-OpenAI Agents in Active Development 🚧
- 🌎 Multilingual UI:
  - English, 中文, Deutsch, Español, Français, Italiano, Polski, Português Brasileiro,
  - Русский, 日本語, Svenska, 한국어, Tiếng Việt, 繁體中文, العربية, Türkçe, Nederlands, עברית
- 🎨 Customizable Dropdown & Interface: Adapts to both power users and newcomers
- 📧 Verify your email to ensure secure access
- 🗣️ Chat hands-free with Speech-to-Text and Text-to-Speech magic
  - Automatically send and play Audio
  - Supports OpenAI, Azure OpenAI, and Elevenlabs
- 📥 Import Conversations from LibreChat, ChatGPT, Chatbot UI
- 📤 Export conversations as screenshots, markdown, text, json
- 🔍 Search all messages/conversations
- 🔌 Plugins, including web access, image generation with DALL-E-3 and more
- 👥 Multi-User, Secure Authentication with Moderation and Token spend tools
- ⚙️ Configure Proxy, Reverse Proxy, Docker, & many Deployment options:
  - Use completely local or deploy on the cloud
- 📖 Completely Open-Source & Built in Public
- 🧑‍🤝‍🧑 Community-driven development, support, and feedback

# librechat_customize

Goal…
使えるようにする。

OPENAI_API_KEY を設定する.env に
自分の普段使っている chatGPT から取得できる
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

### process

pnpm install 完了
client 配下でも pnpm install 完了

足りてない uuid とか install して、3090 も pnpm run dev(vite)で立ち上がった。

3080 でも、90 でも画面で検索しようとすると「キーが見つかりません」エラー。

OPENAI_API_KEY
に上記の api key つけてみた。

上記エラーは解決。
しかし検索しても何も返ってこない。
docker-compose 上はちゃんと Request 飛んで、meilisearch が反応している。

api 配下でも pnpm install した。
結果変わらず。
3.5 でも変わらず。

[OpenAIClient.chatCompletion][stream] API error
log に出てるこれが気になる。

CONFIG_PATH
を活性化
&
https://github.com/danny-avila/LibreChat/discussions/2650
↑ これ参考にして、
docker-compse.yml の api の volume に下記を追加すると、 - ./librechat.yaml:/app/librechat.yaml
docker 立ち上げた時の error はなくなり LibreChat のいい感じの log が出るようになったが、まだ画面で結果は返ってこず&上記の APIerror は出続けている。

### docker 立ち上げた時の error なくなってから

GROQ_API_KEY 活性化
https://console.groq.com/keys
groq のサイトアクセスして API Key を取得
↓
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

https://console.mistral.ai/api-keys/
Mistral API も key 取得(billing 設定しないといけなかったが、2024/9/20 までの free trial でかいくぐった。)
↓
N0g6QWnHo3IohyBKc6RP3jjhO9CVkWgg

できたぁ！！
結局
https://techmebrains.co.jp/knowledge/errorlog/you-exceeded-your-current-quota-please-check-your-plan/
ここに記載の通り、
You exceeded your current quota, please check your plan and billing details. 
が悪かった。
ChatGPT API の billing setting でクレカ登録して 10 ドル突っ込んだらいけた。
