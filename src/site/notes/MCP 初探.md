---
{"dg-publish":true,"permalink":"/MCP 初探/","noteIcon":"default"}
---


1. 什么是 MCP？

MCP 就是一种 LLM 能够识别的协议。为了增强 LLM 的能力而生。如何增强它的能力？本质就是让其他服务、工具按照这个通用协议实现一些功能，然后让 LLM 调用。
因为在有 MCP 之前，LLM 只能做一些在它的训练数据集范围之内的事情，后面即使有了联网搜索能力，但它能做的事情还是有限。比如我想让他帮我打开邮箱服务，发送邮件，它肯定做不到，最起码一点它无法与邮箱客户端进行交流。当有了 MCP 协议, 根据这个协议，实现一个服务，其内部可以调用邮箱服务的接口进行发送、接收邮件。然后把这个服务暴露给 LLM, 之后再跟它进行聊天时，可以直接触发发送邮件服务。


以 Claude desktop 为例：

```mermaid
sequenceDiagram
    actor User as 用户
    participant Client as 客户端
    participant Claude as Claude
    participant MCP as MCP服务器
    participant Tool as 工具执行
    
    User ->> Client: 提出问题
    Client ->> Claude: 1. 发送问题
    
    Note over Claude: 2. 分析可用工具<br>决定使用哪些工具
    
    Claude ->> Client: 3. 请求执行工具
    Client ->> MCP: 调用选定的工具
    MCP ->> Tool: 执行工具操作
    Tool -->> MCP: 返回工具执行结果
    MCP -->> Client: 返回工具结果
    Client -->> Claude: 4. 发送工具结果
    
    Note over Claude: 5. 根据工具结果<br>生成自然语言回答
    
    Claude -->> Client: 返回生成的响应
    Client -->> User: 6. 显示回答
```

上述的客户端即为 Claude Desktop, 也可以是 Cursor。它们的后端对应着 LLM。这里容易混淆。比如用户使用 cursor ，输入问题，cursor 客户端调用远程的 LLM 服务。然后它发现有可用的工具，并且与用户输入的需求匹配，那么它就会返回客户端，客户端此时就能决定使用哪个工具。
于是向 MCP 服务器发送请求。服务器里面定义了一系列工具，此时会选定某个工具，并执行。之后将执行结果返回，一直返回到客户端，客户端让LLM 把结果进行一定的语言重新组织，然后输出给客户端，此时就是用户在客户端（Claude Desktop）上看到的信息。


客户端需要知道 mcp 服务器定义在哪，以及如何调用并运行。常见的是使用 command 进行调用。这样有两种方式：
1. json 配置文件：
```json
{
    "mcpServers": {
        "weather": {
            "command": "uv",
            "args": [
                "--directory",
                "D:\\WORK\\AI_workstation\\weather",
                "run",
                "weather.py"
            ]
        }
        "other server": {
            "command": "uv",
            "args": [
                "--directory",
                "path to the server file dir",
                "run",
                "server script"
            ]
        }
    }
}
```
> Claude Desktop 的配置文件是 `claude_desktop_config.json`

该配置文件就是一个 json 对象，key 就是 “mcpServers",  上面的例子就是在告诉外界，在哪里以及如何运行 weather.py 这个 mcp 服务。

2. 另外一种方式就是直接写出命令行，比如在 cursor 中 MCP Servers 的配置可以是这样：`cmd /k npx -y @smithery/cli@latest run @wopal/mcp-server-hotnews --config {1,2,3}`
它等效于在配置文件 `.cursor/mcp.json` 这样写：
```json
{
    "mcpServers": {
      "@wopal-mcp-server-hotnews": {
        "command": "cmd /k npx",
        "args": [
          "-y",
          "@smithery/cli@latest",
          "run",
          "@wopal/mcp-server-hotnews",
          "--config",
          "{1,2,3}"
        ]
      }
    }
}
```


配置完成后，可以看到有可用的 MCP 工具：
![image.png](https://fastly.jsdelivr.net/gh/Cactusinhand/images_repo/images/202503110040791.png)
	

2. 如何搭建个人 mcp server

可以在这里找：

- https://smithery.ai/
- https://github.com/punkpeye/awesome-mcp-servers
- https://github.com/modelcontextprotocol/servers

3. 搭建 mcp Client

比较复杂




```mermaid
sequenceDiagram
    actor User as 用户
    participant Client as MCP客户端
    participant Claude as Claude AI
    participant Server as MCP服务器
    participant Tools as 工具执行
    
    Note over User, Tools: 初始化阶段
    User ->> Client: 启动客户端<br>(uv run client.py server.py)
    Client ->> Server: 连接服务器
    Server -->> Client: 确认连接
    Client ->> Server: 请求可用工具列表
    Server -->> Client: 返回工具列表
    Client -->> User: 显示可用工具和启动提示
    
    Note over User, Tools: 对话循环
    loop 交互会话
        User ->> Client: 输入查询
        
        Client ->> Claude: 发送查询和工具描述
        
        Note over Claude: 分析查询并决定<br>是否使用工具
        
        alt 需要使用工具
            Claude ->> Client: 请求执行工具调用
            Client ->> Server: 转发工具调用请求
            Server ->> Tools: 执行指定工具
            Tools -->> Server: 返回执行结果
            Server -->> Client: 返回工具结果
            Client -->> Claude: 发送工具执行结果
        end
        
        Claude -->> Client: 生成最终响应
        Client -->> User: 显示响应
    end
    
    User ->> Client: 输入"quit"
    Client ->> Server: 关闭连接
    Client -->> User: 结束会话
```




参考： https://modelcontextprotocol.io/introduction