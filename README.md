<div align="center">
  <img src="https://assets.alicdn.com/g/qwenweb/qwen-webui-fe/0.0.201/favicon.png" alt="Qwen Logo" width="120" height="120">

  <h1>Qwen API</h1>

  <p>
    <strong>OpenAI-compatible API endpoints for Qwen AI</strong>
  </p>

  <p>
    <a href="#-key-features">Features</a> •
    <a href="#-quick-start">Quick Start</a> •
    <a href="#️-supported-endpoints">Supported Endpoints</a> •
    <a href="#-openapi-docs">OpenAPI Docs</a> •
    <a href="#-usage-examples">Usage Examples</a> •
    <a href="#-license">License</a>
  </p>

  <br/>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/MAJOR_UPDATE-August_31,_2026-7c3aed?style=for-the-badge" alt="Major Update">
</p>

> [!IMPORTANT]
> ### 🚀 Major Update — August 31, 2026
>
> - Fixed image generation and editing; added `url` and `b64_json` outputs.
> - Added text-to-video and image-to-video with URL, base64, or uploaded image input.
> - Fixed conversation history and follow-ups across Chat, Web Dev, Full Stack, Slides, and Deep Research.
> - Added Fast, Auto, and Thinking modes with OpenAI `reasoning_effort` support.
> - Improved web search with clickable citations and OpenAI-compatible annotations.
> - Expanded multimodal support for images, audio, video, PDF, PPTX, DOCX, and other documents.
> - Upgraded Deep Research with normal/advanced modes, media attachments, reasoning output, citations, and PDF/Markdown downloads.
> - Added Slides generation with preview images and downloadable PDF.
> - Improved tool calling, model compatibility, validation, and OpenAI-style error responses.

## 🌟 Overview

Qwen API bridges the `chat.qwen.ai` Web API with familiar OpenAI-compatible endpoints. It supports Chat Completions, multimodal inputs, web search, reasoning summaries, function calling, image and video generation, Deep Research, Web Development, Full-Stack artifacts, and Slides.

> **Note**: This is an unofficial proxy and not affiliated with Alibaba Cloud or Qwen AI.

> **Compatibility scope**: The primary compatibility target is OpenAI Chat Completions plus Images-style generation responses. Qwen-specific capabilities use documented extensions such as `thinking_mode`, `reasoning_content`, `file_url`, and `video_url`.

## 📘 OpenAPI Docs

### API documentation : https://qwen-api.readme.io/

- **Spec file**: `qwen.json` (OpenAPI 3.1.0)
- **What it is**: OpenAPI-ready API documentation covering all endpoints, OpenAI-compatible request/response shapes, security, and examples.
- **How to use**:
  - Import `qwen.json` into Swagger UI, Redocly, Postman, Bruno, or Insomnia.
  - Generate typed clients with your preferred tool (e.g., `openapi-generator`, `orval`).
- **Servers**: Defaults to `https://qwen.aikit.club`; you can change the `host` variable or edit the server URL after import.

## 🚀 Key Features

| Feature                     | Description                                                |
| --------------------------- | ---------------------------------------------------------- |
| 🔁 **OpenAI Compatibility** | Drop-in replacement for OpenAI API calls                   |
| 💬 **Chat Completions**     | Text-based conversations with all Qwen models              |
| 🎨 **Image Generation**     | Create stunning images from text prompts                   |
| ✏️ **Image Editing**        | Modify existing images with text instructions              |
| 🎬 **Video Generation**     | Transform text or images into video content                |
| 🔬 **Deep Research**        | Comprehensive research with web search and citations       |
| 👨🏻‍💻 **Web Development**      | Generate interactive web components and UI elements        |
| 🏗️ **Full-Stack Apps**      | Complete application development from frontend to backend  |
| 📊 **Slides Generation**    | Create professional presentations with AI-generated slides |
| 🔍 **Web Search**           | Enable web search capabilities in conversations            |
| 🧠 **Thinking Mode**        | Activate reasoning mode for complex problem solving        |
| 👁️ **Vision Support**       | Analyze images, PDFs, and visual content                   |
| 📁 **Multimodal Files**     | Support for image, audio, video, and document uploads      |
| 🌍 **CORS Support**         | Full cross-origin resource sharing support                 |
| 🔧 **Custom Tool Calling**  | OpenAI-compatible function/tool calling for select models  |
| ⚡ **Edge Performance**     | Lightning-fast global deployment via Cloudflare Workers    |

## 🛠️ Supported Endpoints

| Endpoint                 | Method      | Description           |
| ------------------------ | ----------- | --------------------- |
| `/v1/validate`           | GET/POST    | Validate token        |
| `/v1/refresh`            | GET/POST    | Refresh token         |
| `/v1/models`             | GET         | List available models |
| `/v1/chat/completions`   | POST        | Chat completions      |
| `/v1/images/generations` | POST        | Generate images       |
| `/v1/images/edits`       | POST        | Edit existing images  |
| `/v1/videos/generations` | POST        | Generate videos       |
| `/v1/chats/delete`       | DELETE/POST | Delete all chats      |

Unknown routes redirect to `https://chat.qwen.ai`. API errors use an OpenAI-style `{ "error": { ... } }` envelope.

## 🧠 Currently Available Models

| Model ID                           | Model Name               | 👁️ Vision | 💡 Thinking | 🌐 Search | 🔧 Tools |
| ---------------------------------- | ------------------------ | --------- | ----------- | --------- | -------- |
| `qwen3.8-max`                      | Qwen3.8-Max              | ✅        | ✅          | ✅        | ✅       |
| `qwen3.7-plus`                     | Qwen3.7-Plus             | ✅        | ✅          | ✅        | ✅       |
| `qwen3.7-max`                      | Qwen3.7-Max              | ❌        | ✅          | ❌        | ✅       |
| `qwen3.6-plus`                     | Qwen3.6-Plus             | ✅        | ✅          | ✅        | ✅       |
| `qwen3.5-plus`                     | Qwen3.5-Plus             | ✅        | ✅          | ✅        | ✅       |
| `qwen3.5-omni-plus`                | Qwen3.5-Omni-Plus        | ✅        | ❌          | ❌        | ❌       |
| `qwen3-coder-plus`                 | Qwen3-Coder              | ✅        | ❌          | ❌        | ✅       |

### Specialized Models

| Model ID             | Purpose                                |
| -------------------- | -------------------------------------- |
| `qwen-image`         | Image generation and editing           |
| `qwen-video`         | Video generation and understanding     |
| `qwen-deep-research` | Deep research and report generation    |
| `qwen-web-dev`       | Web development                        |
| `qwen-full-stack`    | Full-stack application development     |
| `qwen-slides`        | Presentation generation                |

## 🚀 Quick Start

### Use the Public Instance

The public instance is available at: `https://qwen.aikit.club`

## 💡 Usage Examples

### Authentication

The proxy requires a Bearer token containing Qwen credentials:

```javascript
const headers = {
  Authorization: "Bearer YOUR_QWEN_ACCESS_TOKEN",
  "Content-Type": "application/json",
};
```

### Temporary Free Token

For quick testing, you can use this temporary token until it expires.

- Token:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYyYThjOTE1LWRmMzgtNGVmMi1hNWMxLWY1M2IyNjdkYmQzNCIsImxhc3RfcGFzc3dvcmRfY2hhbmdlIjoxNzg4MTU5NTA3LCJleHAiOjE3OTA3NTE2Mzd9.Vqbr_27Px1YwF94xCv08sY-RbWbjvvuRKkj-CWeci8I
```

- Expires: 2026-09-30 07:00:37 UTC (2026-09-30 12:30:37 IST, UTC+05:30)
- Note: This token is for evaluation only and will stop working after the expiration time.

### How to Get Your Token

To obtain your Qwen API token, follow these steps:

1. **Visit Qwen Chat**: Go to [chat.qwen.ai](https://chat.qwen.ai) and log in to your account
2. **Run the Token Extractor**: Copy and paste the following JavaScript code into your browser's developer console (press F12 → Console tab):

```javascript
javascript: (function () {
  if (window.location.hostname !== "chat.qwen.ai") {
    alert("🚀 This code is for chat.qwen.ai");
    window.open("https://chat.qwen.ai", "_blank");
    return;
  }
  function getApiKeyData() {
    const token = localStorage.getItem("token");
    if (!token) {
      alert("❌ qwen access_token not found !!!");
      return null;
    }
    return token;
  }
  async function copyToClipboard(text) {
    try {
      await navigator.clipboard.writeText(text);
      return true;
    } catch (err) {
      console.error("❌ Failed to copy to clipboard:", err);
      const textarea = document.createElement("textarea");
      textarea.value = text;
      textarea.style.position = "fixed";
      textarea.style.opacity = "0";
      document.body.appendChild(textarea);
      textarea.focus();
      textarea.select();
      const success = document.execCommand("copy");
      document.body.removeChild(textarea);
      return success;
    }
  }
  const apiKeyData = getApiKeyData();
  if (!apiKeyData) return;
  copyToClipboard(apiKeyData).then((success) => {
    if (success) {
      alert("🔑 Qwen access_token copied to clipboard !!! 🎉");
    } else {
      prompt("🔰 Qwen access_token:", apiKeyData);
    }
  });
})();
```

3. **Get Your Token**: The script will automatically:
   - Extract your access_token from localStorage
   - Copy the access_token to your clipboard

4. **Use the Token**: The copied token is now ready to use as your `Bearer` token in API requests

**Important Notes:**

- ⚠️ This script only works on chat.qwen.ai - make sure you're logged in
- 🔒 Keep your token secure - it provides access to your Qwen account
- 🔄 You may need to regenerate the token periodically if it expires

### Validate Token (from JS snippet)

Validate the access_token produced by the browser JS snippet above.

```bash
curl -X POST https://qwen.aikit.club/validate \
  -H "Content-Type: application/json" \
  -d '{"token": "YOUR_QWEN_ACCESS_TOKEN"}'
```

Or via GET:

```bash
curl "https://qwen.aikit.club/validate?token=YOUR_QWEN_ACCESS_TOKEN"
```

### Chat Completions

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [{ role: "user", content: "Hello, how are you?" }],
    stream: false,
  }),
});
```

### Conversation Follow-Ups

Responses include hidden continuation metadata inside the assistant content:

```html
<!-- qwen_metadata: {"response_id":"...","request_id":"..."} -->
```

Keep the complete assistant response in the next `messages` array. The proxy extracts this metadata, continues the same upstream Qwen chat, and removes the metadata before sending conversation text upstream. This enables follow-ups for normal chat, Web Development, Full-Stack artifacts, Slides, and Deep Research.

### Image Generation

```javascript
const response = await fetch("https://qwen.aikit.club/v1/images/generations", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    prompt: "A beautiful sunset over mountains",
    size: "1024x1024",
  }),
});
```

Set `response_format` to `"b64_json"` to receive `data[0].b64_json` instead of a temporary URL. The default is `"url"`.

### Image Editing

Image editing accepts exactly one source image. Requests containing multiple `image`/`image[]` fields or a JSON image array are rejected with HTTP 400.

```javascript
// Using FormData for file upload
const formData = new FormData();
formData.append("image", imageFile); // File object
formData.append("prompt", "Change the sky to a starry night");
formData.append("response_format", "b64_json"); // Optional; default is "url"

const response = await fetch("https://qwen.aikit.club/v1/images/edits", {
  method: "POST",
  headers: {
    Authorization: "Bearer YOUR_QWEN_ACCESS_TOKEN",
  },
  body: formData,
});

// Or using JSON with image URL/base64
const response = await fetch("https://qwen.aikit.club/v1/images/edits", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    image: "https://example.com/image.jpg", // or base64 data URL
    prompt: "Add a rainbow in the background",
  }),
});
```

### Web Search Mode

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [{ role: "user", content: "What are the latest AI developments?" }],
    web_search_options: { search_context_size: "medium" },
  }),
});
```

The legacy `tools: [{ type: "web_search" }]` form remains supported for backward compatibility.

### Thinking Mode

Use `thinking_mode` to select Qwen's current reasoning behavior:

- `fast` (default): No thinking summary; returns the answer directly.
- `auto`: Qwen decides whether to reason and returns any summary as OpenAI-compatible `reasoning_content`.
- `thinking`: Forces reasoning and returns the summary as OpenAI-compatible `reasoning_content`.

The legacy `enable_thinking` flag remains supported: `true` maps to `thinking` and `false` maps to `fast`. The former `thinking_budget` parameter is no longer sent upstream.

OpenAI Chat Completions SDKs can use the standard `reasoning_effort` field. The proxy maps `none`/`minimal` to `fast`, `low`/`medium` to `auto`, and `high`/`xhigh`/`max` to `thinking`. If multiple controls are supplied, precedence is `thinking_mode`, then `reasoning_effort`, then legacy `enable_thinking`.

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [{ role: "user", content: "Solve this complex math problem: ..." }],
    reasoning_effort: "high",
  }),
});
```

### Custom Tool/Function Calling

Qwen's web API (`chat.qwen.ai`) does not natively support tool/function calling — unlike the official DashScope API, the web reverse API has no built-in tool calling capability. This proxy bridges that gap by implementing **OpenAI-compatible tool calling** via prompt engineering with XML-based parsing, enabling standard OpenAI `tools` and `tool_choice` parameters on the web API.

**Supported model IDs**: `qwen3.8-max`, `qwen3.7-plus`, `qwen3.7-max`, `qwen3.6-plus`, `qwen3.5-plus`, `qwen3-coder-plus`

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.6-plus",
    messages: [{ role: "user", content: "What's the weather in Tokyo?" }],
    tools: [
      {
        type: "function",
        function: {
          name: "get_weather",
          description: "Get the current weather for a location",
          parameters: {
            type: "object",
            properties: {
              location: { type: "string", description: "City name" },
            },
            required: ["location"],
          },
        },
      },
    ],
    tool_choice: "auto",
    stream: true,
  }),
});
```

**Supported `tool_choice` values:**

- `"auto"` / `"required"` — Model must use at least one tool (first turn), decides freely on subsequent turns
- `"none"` — No tools, plain text response only
- `{ "type": "function", "function": { "name": "xyz" } }` — Force a specific tool

Tool calling still instructs Qwen to emit XML as the primary format:
`<tool_calls>[{"name":"tool_name","arguments":{}}]</tool_calls>`.
Internally, the proxy also accepts a few fallback formats from Qwen output and maps qwen-safe tool aliases back to the original client tool names. External clients should continue sending normal OpenAI `tools`, `tool_choice`, and `messages`; response `tool_calls` use the original names.

### Video Generation

The same endpoint performs text-to-video when `image` is omitted and image-to-video when it is provided. `prompt` is required; `image`, `size`, and `response_format` are optional. Image-to-video accepts at most one source image; repeated `image`/`image[]` fields or a JSON image array are rejected with HTTP 400. `response_format: "b64_json"` returns the complete MP4 in `data[0].b64_json`; this is a proxy extension because OpenAI's Videos API downloads bytes through a separate content endpoint. The default remains `"url"`.

```javascript
const response = await fetch("https://qwen.aikit.club/v1/videos/generations", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    prompt: "A cat playing with a ball of yarn in slow motion",
    size: "1280x720",
  }),
});
```

For image-to-video, pass an image URL or base64 data URL in JSON:

```javascript
const response = await fetch("https://qwen.aikit.club/v1/videos/generations", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    prompt: "The subject slowly turns toward the camera",
    image: "https://example.com/source.jpg",
    size: "16:9",
  }),
});
```

Or upload a local image with multipart form data:

```javascript
const formData = new FormData();
formData.append("prompt", "The subject slowly turns toward the camera");
formData.append("image", imageFile);
formData.append("size", "16:9");

const response = await fetch("https://qwen.aikit.club/v1/videos/generations", {
  method: "POST",
  headers: { Authorization: "Bearer YOUR_QWEN_ACCESS_TOKEN" },
  body: formData,
});
```

### Deep Research

Deep Research supports the same image, audio, video, and document attachments as normal multimodal chat, using the same URL/base64 upload flow. `tools` and `web_search_options` are not supported. Research planning is returned as OpenAI-compatible `reasoning_content`, while the completed report is returned as normal assistant `content` with citation and download links.

The default is normal research. Use the standard OpenAI `reasoning_effort` field with `medium`, `high`, `xhigh`, or `max` to select advance research. Omitted, `none`, `minimal`, or `low` use normal research. For compatibility, `thinking_mode: "thinking"` or `enable_thinking: true` also select advance research; `thinking_mode: "fast"`/`"auto"` or `enable_thinking: false` select normal research. Precedence is `thinking_mode`, then `reasoning_effort`, then `enable_thinking`; `thinking_budget` is ignored. The first turn may ask clarifying questions; include its assistant response in the next Chat Completions request so the hidden metadata can continue the same Deep Research chat.

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-deep-research",
    messages: [
      {
        role: "user",
        content: "Research the latest developments in quantum computing",
      },
    ],
    stream: false,
  }),
});
```

### Web Development (qwen-web-dev)

The `qwen-web-dev` model is specialized for frontend web development, creating interactive web components, HTML/CSS/JavaScript code, and providing live preview capabilities.

**Features:**

- HTML/CSS/JavaScript code generation
- Interactive UI components
- Responsive design support
- Real-time preview generation
- Framework support: React, Vue, Vanilla JS, HTML5
- Styling: Tailwind CSS, Bootstrap

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-web-dev",
    messages: [
      {
        role: "user",
        content:
          "Create a responsive navigation bar with a logo, menu items, and a mobile hamburger menu using HTML, CSS, and vanilla JavaScript",
      },
    ],
    stream: false,
  }),
});
```

**Example Output:**
The model will generate complete, production-ready web components with:

- Clean, semantic HTML structure
- Modern CSS with responsive breakpoints
- Vanilla JavaScript for interactivity
- Mobile-first design approach
- Accessibility considerations

### Full-Stack Development (qwen-full-stack)

The `qwen-full-stack` model handles complete application development, from frontend to backend, database design, API development, and system architecture.

**Features:**

- Frontend and backend code generation
- Database schema design
- RESTful and GraphQL API development
- Authentication and authorization
- Microservices architecture
- Deployment-ready code
- Multi-language support: JavaScript, TypeScript, Python, Java, Go, PHP
- Frameworks: React, Vue, Angular, Node.js, Express, Django, Flask, Spring Boot

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-full-stack",
    messages: [
      {
        role: "user",
        content:
          "Create a complete REST API for a task management system with user authentication, CRUD operations for tasks, and a React frontend. Use Node.js/Express for the backend and MongoDB for the database.",
      },
    ],
    stream: false,
  }),
});
```

**Example Full-Stack Application:**

```javascript
// Advanced example: Building a complete blog platform
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-full-stack",
    messages: [
      {
        role: "user",
        content: `Build a complete blog platform with the following requirements:

Backend (Node.js/Express):
- User authentication with JWT
- CRUD operations for blog posts
- Comment system
- Like/bookmark functionality
- Image upload support
- RESTful API endpoints

Frontend (React):
- Home page with post listings
- Post detail page with comments
- Create/Edit post interface
- User profile page
- Responsive design with Tailwind CSS

Database (MongoDB):
- User schema with authentication
- Post schema with relationships
- Comment schema
- Proper indexing for performance`,
      },
    ],
    stream: false,
  }),
});
```

**Key Differences:**

| Feature          | qwen-web-dev                               | qwen-full-stack                    |
| ---------------- | ------------------------------------------ | ---------------------------------- |
| **Focus**        | Frontend UI/UX                             | Complete application stack         |
| **Code Output**  | HTML, CSS, JavaScript                      | Frontend + Backend + Database      |
| **Use Cases**    | Web components, landing pages, UI elements | Complete apps, APIs, microservices |
| **Complexity**   | Simple to moderate                         | Moderate to complex                |
| **Architecture** | Client-side only                           | Full system architecture           |

### Slides Generation (qwen-slides)

The `qwen-slides` model generates professional presentations with AI-generated slide images and a downloadable PDF. It researches the topic, creates content, and renders visual slides automatically.

**Features:**

- AI-powered slide content generation
- Web search for up-to-date information
- Auto-generated slide images for each page
- Downloadable PDF of the full presentation
- Thinking summary with research insights

```javascript
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-slides",
    messages: [
      {
        role: "user",
        content: "Create a presentation on the history and future of artificial intelligence",
      },
    ],
    stream: false,
  }),
});
```

**Example Output:**
The response includes:

- **Reasoning content**: Thinking summary with research insights
- **Text content**: Written description of each slide
- **Slide images**: Markdown image links for each generated slide
- **PDF link**: A downloadable PDF of the complete presentation

```javascript
// Streaming example with thinking enabled
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen-slides",
    messages: [
      {
        role: "user",
        content:
          "Make a 10-slide pitch deck for a SaaS startup that provides AI-powered customer support",
      },
    ],
    stream: true,
  }),
});
```

### Delete All Chats

```javascript
// Using DELETE method
const response = await fetch("https://qwen.aikit.club/v1/chats/delete", {
  method: "DELETE", // GET and POST are also supported
  headers: headers,
});
```

## 📁 Multimodal File Support

The API supports various file formats for comprehensive multimodal interactions:

> **⚠️ Important Limitation**: **Image, Audio, and Video are different media types within the media group. Do not mix different media types in one request** (for example, image + audio, image + video, or audio + video). Multiple images are allowed, while audio and video are limited to one file each. Documents are a separate group and may be combined with one supported media type (for example, image + PDF or audio + DOCX), subject to the limits below.

### Supported File Types

- **Media Files** _(media group)_:
  - **Images**: **JPG, PNG, GIF, WebP** _(most common)_, BMP, TIFF, ICO, ICNS, JFIF, JP2
  - **Audio**: **MP3, WAV, M4A, AAC** _(most common)_, AMR
  - **Video**: **MP4, MOV, AVI, MKV** _(most common)_, WMV, FLV
- **Documents** _(separate category)_: **PDF, TXT, MD** _(most common)_, DOC, DOCX, PPT, PPTX, CSV, XLS, XLSX

> **💡 Tip**: Bold formats are the most commonly used and recommended for best compatibility.

### 📏 File Limits

The following Qwen live runtime limits apply to multimodal file uploads. The proxy forwards uploads to Qwen and does not pre-enforce these limits itself. A selected model's `file_limits` configuration may override these defaults:

| File Type     | Max Size (MB) | Max Count | Max Duration (seconds) |
| ------------- | ------------- | --------- | ---------------------- |
| **Images**    | 20            | 5         | -                      |
| **Audio**     | 2,000         | 1         | 10,800                 |
| **Video**     | 2,000         | 1         | 3,600                  |
| **Documents** | 20            | 5         | -                      |
| **Default**   | 20            | -         | -                      |

> **📋 Summary**: You can upload up to 5 images (20 MB each), 1 audio file (2,000 MB, 3 hours), 1 video file (2,000 MB, 1 hour), or 5 documents (20 MB each) per request.

Additional Qwen limits:

- **Agent Mode**: Maximum 10 files, 20 MB per file, and 50 MB total.
- **Image Edit**: Exactly 1 input image through this proxy.
- **Model overrides**: The selected model's live `file_limits` configuration takes precedence over the defaults above.

> **Upload fallback**: Attachment handling is best-effort. If an attachment cannot be downloaded or uploaded, the proxy skips that attachment and continues the request as text-only so the user can still receive a response.

### ✅ Valid Combinations

- ✅ Multiple images
- ✅ Multiple documents
- ✅ Image + PDF
- ✅ Image + DOCX/PPTX
- ✅ Audio + PDF
- ✅ Audio + DOCX/PPTX
- ✅ Video + PDF
- ✅ Video + DOCX/PPTX
- ✅ A single image, audio, or video

### ❌ Invalid Combinations

- ❌ Image + Audio
- ❌ Image + Video
- ❌ Audio + Video
- ❌ Multiple videos
- ❌ Multiple audio files

### Vision-Style Multimodal Chat

```javascript
// Analyze any supported file type using standard chat completions
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [
      {
        role: "user",
        content: [
          { type: "text", text: "What do you see in this image?" },
          {
            type: "image_url",
            image_url: {
              url: "https://download.samplelib.com/png/sample-hut-400x300.png",
              // or use base64: "data:image/jpeg;base64,..."
            },
          },
        ],
      },
    ],
  }),
});
```

### Valid Multimodal Combination (Image + PDF)

```javascript
// ✅ VALID: Combine different categories (Media + Document)
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [
      {
        role: "user",
        content: [
          { type: "text", text: "Analyze this image and PDF document together" },
          {
            type: "image_url",
            image_url: { url: "https://download.samplelib.com/png/sample-hut-400x300.png" },
          },
          {
            type: "file_url",
            file_url: { url: "https://pdfobject.com/pdf/sample.pdf" },
          },
        ],
      },
    ],
  }),
});
```

### ❌ Invalid Combinations (Don't Do This)

```javascript
// ❌ INVALID: Cannot combine image + video (same category)
const response = await fetch("https://qwen.aikit.club/v1/chat/completions", {
  method: "POST",
  headers: headers,
  body: JSON.stringify({
    model: "qwen3.8-max",
    messages: [
      {
        role: "user",
        content: [
          { type: "text", text: "This will not work properly" },
          {
            type: "image_url",
            image_url: { url: "https://download.samplelib.com/png/sample-hut-400x300.png" },
          },
          {
            type: "video_url",
            video_url: { url: "https://download.samplelib.com/mp4/sample-10s.mp4" },
          },
          // ❌ Cannot mix media files (image, audio, video)
        ],
      },
    ],
  }),
});
```

## ⚠️ Important Limitations

- This project wraps the `chat.qwen.ai` Web API, not the official DashScope API.
- Generated image, video, Slides, PDF, and Markdown URLs may be signed or temporary. Download important assets promptly or request `b64_json` where supported.
- Image editing accepts exactly one input image. Image-to-video accepts at most one source image.
- Deep Research first collects the complete upstream research response, then returns/re-streams formatted `reasoning_content` followed by final `content`.
- Upload processing is best-effort: an attachment that cannot be downloaded or uploaded may be skipped so the request can continue as text.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">
  <p>
    <sub>Built with ❤️ by Tarun</sub>
  </p>
  <p>
    <sub>If you find this project useful, please consider giving it a ⭐ on GitHub!</sub>
  </p>
</div>
