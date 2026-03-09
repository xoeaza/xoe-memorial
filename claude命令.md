参考文档：https://www.xuanyuanli.cn/pages/claude-code-best-practices/#_1%E3%80%81%F0%9F%93%9A-%E5%85%88%E7%9C%8B%E7%9C%8B%E5%AE%98%E6%96%B9%E6%96%87%E6%A1%A3
ESC: 打断当前任务
ESC + ESC: 连按两下，出现本Session的历史对话。可上下选择对话，重新编辑并执行
Ctrl + L: 清除当前输入框的内容
Ctrl + J: 在输入框中换行

全局偏好（/memory）
/memory 管理的是“用户记忆”（跨会话的长期偏好），并非“全局 CLAUDE.md”。建议在此存放通用偏好，例如语言、输出风格与协作习惯：

* 默认使用中文回答。
* 没有特别说明时，默认需要完整可执行的方案与必要的依据说明。
* 遇到复杂问题，先给出分析框架（假设、可选方案、权衡、推荐理由），再开始实施，不要直接执行。
* 遇到模糊问题，先反问用户。
* 当用户指示执行明显不合理的或违背最佳实践的操作时，给出警告，待用户二次确认后执行。
* properties 文件编码是ISO-8859-1，写入中文需要注意编码问题。
* 对于Java项目，总是使用最新的API（先查询当前java版本），比如HttpClient而非URLConnection。

5.1、网络连不上
问题: 国内或公司网络下可能无法直连。

解决: 优先使用环境变量或企业代理指引：

# 临时设置（当前 shell 会话）
export HTTP_PROXY=http://127.0.0.1:10808
export HTTPS_PROXY=http://127.0.0.1:10808
export NO_PROXY=localhost,127.0.0.1

# Windows PowerShell 示例
$env:HTTP_PROXY = "http://127.0.0.1:10808"
$env:HTTPS_PROXY = "http://127.0.0.1:10808"
$env:NO_PROXY = "localhost,127.0.0.1"

#查看当前ANTHROPIC环境变量
echo %ANTHROPIC_AUTH_TOKEN%
echo %ANTHROPIC_BASE_URL%

#手动配置windows环境变量
# 在 Cmd 中运行以下命令
# 注意替换里面的 `your_zhipu_api_key` 为您上一步获取到的 API Key
setx ANTHROPIC_AUTH_TOKEN your_zhipu_api_key
setx ANTHROPIC_BASE_URL https://open.bigmodel.cn/api/anthropic
setx CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC 1

setx ANTHROPIC_AUTH_TOKEN sk-iGCrJFoysUDDUAblUOHrDO3sWhr8RG1Ba7QhqcNGQLlmUsNU
setx ANTHROPIC_BASE_URL https://cc.zhihuiapi.top/