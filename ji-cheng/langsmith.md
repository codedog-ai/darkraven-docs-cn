# Langsmith

{% hint style="info" %}
如果您使用了 Langchain 或其他基于 Langchain 封装的框架进行开发，您可以通过 Langsmith SDK 上报 LLM 链路数据到 Darkraven
{% endhint %}

## 安装 Langsmith

{% tabs %}
{% tab title="Python" %}
<pre><code><strong>pip install langsmith
</strong></code></pre>
{% endtab %}
{% endtabs %}

## 创建 API Key

在设置菜单中，进入 API Key 页，创建一个 API Key。

## 配置

为 Langchain 添加如下配置：

{% tabs %}
{% tab title="环境变量" %}
<pre><code><strong>export LANGCHAIN_TRACING_V2=true
</strong>export LANGCHAIN_API_KEY=&#x3C;your-api-key>
export LANGCHAIN_PROJECT=&#x3C;your-project-name>
export LANGCHAIN_ENDPOINT=https://api.darkraven.ai/api/v1/insert
</code></pre>
{% endtab %}
{% endtabs %}

## 其他

关于 Langsmith SDK 更多的功能配置，请参考官方文档：[Tracing](https://docs.smith.langchain.com/how\_to\_guides/tracing)

