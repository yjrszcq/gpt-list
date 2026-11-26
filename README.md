# GPT 分流规则

适用于 OpenAI、ChatGPT、Codex 及相关依赖服务的分流规则，支持 YAML 和 LIST 格式。

## Rule Provider

> 以下两种仅为不同的表示方式，作用相同，二选一即可。

```yaml
gpt: {type: http, format: yaml, behavior: classical, url: "https://raw.githubusercontent.com/yjrszcq/gpt-list/refs/heads/main/gpt.yaml", path: ./ruleset/gpt.yaml, interval: 86400}
```

```yaml
gpt:
  type: http
  format: yaml
  behavior: classical
  url: "https://raw.githubusercontent.com/yjrszcq/gpt-list/refs/heads/main/gpt.yaml"
  path: ./ruleset/gpt.yaml
  interval: 86400
```

## Rules

> 假设你的 `proxy-groups` 中对 GPT 分流的代理组名为 `GPT`。

```yaml
rules:
  # GPT
  - RULE-SET,gpt,GPT
```

## LIST

如果使用 LIST 格式，可采用以下配置：

```yaml
gpt: {type: http, format: text, behavior: classical, url: "https://raw.githubusercontent.com/yjrszcq/gpt-list/refs/heads/main/gpt.list", path: ./ruleset/gpt.list, interval: 86400}
```

## Sources

- [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)
- [水獭 AI 代理分流规则](https://shuita.xyz/rules)
- [OpenAI 官方网络配置文档](https://help.openai.com/en/articles/9247338-network-recommendations-for-chatgpt-errors-on-web-and-apps)
