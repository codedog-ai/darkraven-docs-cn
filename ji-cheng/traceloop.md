# Traceloop

{% hint style="info" %}
如果您使用 Python, Javascript 或其他 Traceloop 支持的编程语言进行开发,   您可以通过 Traceloop SDK 上报 LLM 链路数据到 Darkraven\


完整兼容性请参考：[Traceloop Doc - OpenLLMetry](https://www.traceloop.com/docs/openllmetry/introduction) 和 [Traceloop Doc - What's support ?](https://www.traceloop.com/docs/openllmetry/tracing/supported)
{% endhint %}

## 安装 Traceloop

{% tabs %}
{% tab title="Python" %}
```bash
pip install traceloop-sdk
```
{% endtab %}
{% endtabs %}

## 初始化

{% tabs %}
{% tab title="Python" %}
```python
from opentelemetry.exporter.otlp.proto.http.metric_exporter import OTLPMetricExporter
from opentelemetry.exporter.otlp.proto.http.trace_exporter import OTLPSpanExporter
from traceloop.sdk import Traceloop


app_name="LLM 应用标识"
trace_endpoint="https://api.darkraven.com/api/v1/insert/trace-otlp"
metric_endpoint="https://api.darkraven.com/api/v1/insert/metric-otlp"
apikey="Darkraven API Key"

traces_exporter = OTLPSpanExporter(
    endpoint=trace_endpoint,
    headers={"apikey":apikey}
)
    
metrics_exporter = OTLPMetricExporter(
    endpoint_metric_endpoint,
    headers={"apikey":apikey}
)

Traceloop.init(
    app_name=app_name,
    exporter=traces_exporter,
    metrics_exporter=metrics_exporter
)
```
{% endtab %}
{% endtabs %}

## 其他

如果您需要自定义埋点或其他功能，请参考：[Traceloop Doc - Workflow Annotations](https://www.traceloop.com/docs/openllmetry/tracing/annotations) 与其他相关文档
