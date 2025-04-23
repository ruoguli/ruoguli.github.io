---
title: Python调用DeepSeek的API
date:   2025-01-12 12:00:00 +0800
categories: [Deepseek]
tags: [deepseek]
description: 仅供参考
---

1. 以下内容来自DeepSeek的[API文档](https://api-docs.deepseek.com/zh-cn/)。

2. 安装OpenAI的SDK：
```
pip3 install openai
```

3. 示例代码：
```python
from openai import OpenAI  
  
client = OpenAI(api_key="<DeepSeek API Key>", base_url="https://api.deepseek.com")  
  
response = client.chat.completions.create(  
model="deepseek-chat",  
messages=[  
{"role": "system", "content": "You are a helpful assistant"},  
{"role": "user", "content": "Hello"},  
],  
stream=False  
)  
  
print(response.choices[0].message.content)
```

