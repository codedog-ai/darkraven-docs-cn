# Langfuse

{% hint style="info" %}
使用 Python, Javascript 或其他兼容语言开发 LLM 应用时，您可选用 Langfuse SDK 上报 LLM 调用链路数据。

\
查看完整兼容性:&#x20;

\- [Langfuse SDKs - Overview](https://langfuse.com/docs/sdk/overview)

\- [Langfuse Integrations - Overview](https://langfuse.com/docs/integrations/overview)
{% endhint %}

## 安装

安装指南取自 Langfuse 官方文档：[Langfuse SDKs](https://langfuse.com/docs/sdk/overview) .

{% tabs %}
{% tab title="Python" %}
```bash
pip install langfuse
```
{% endtab %}

{% tab title="Javascript" %}
```bash
npm i langfuse
# or
yarn add langfuse
 
# Node.js < 18
npm i langfuse-node
 
# Deno
import { Langfuse } from "https://esm.sh/langfuse"// Some code
```
{% endtab %}
{% endtabs %}

## 设置

1. 在 Darkraven，设置页中，创建一个 API key
2. 通过环境变量添加以下设置

* LANGFUSE\_SECRET\_KEY: 值为刚才创建的 Api key
* LANGFUSE\_PUBLIC\_KEY: 值为刚才创建的 Api key
* LANGFUSE\_HOST: 值为 `https://api.darkraven.ai/api/dify`

## 埋点代码示例

代码示例取自 Langfuse 官方文档：[Langfuse SDKs](https://langfuse.com/docs/sdk/overview). 更多功能使用请参考此文档

{% tabs %}
{% tab title="Python" %}
```python
from langfuse.decorators import observe
from langfuse.openai import openai # OpenAI integration
 
@observe()
def story():
    return openai.chat.completions.create(
        model="gpt-3.5-turbo",
        max_tokens=100,
        messages=[
          {"role": "system", "content": "You are a great storyteller."},
          {"role": "user", "content": "Once upon a time in a galaxy far, far away..."}
        ],
    ).choices[0].message.content
 
@observe()
def main():
    return story()
 
main()
```
{% endtab %}
{% endtabs %}
