# Wikimedia图片搜索服务 Wikimedia Search Images

该MCP服务器使AI助手能够在Wikimedia Commons上搜索图片，提供详细的元数据和可选的缩略图组合，帮助AI模型进行视觉比较。
This MCP server enables AI assistants to search for images on Wikimedia Commons, providing detailed metadata and optional thumbnail combinations to assist AI models in visual comparisons.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| wikimedia_search_images | Search for images on Wikimedia Commons with metadata including download URLs and optional thumbnail composite image for visual comparison. Use results to e.g. fetch full images that are relevant for your task. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659355651](https://mcp.xiaobenyang.com/inspector/1777316659355651)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659355651](https://mcp.xiaobenyang.com/inspector/1777316659355651)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "Wikimedia图片搜索服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659355651/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "Wikimedia图片搜索服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659355651/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "Wikimedia图片搜索服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659355651",
          },
          "transport": "stdio"
        }
      }
}

```
