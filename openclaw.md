<!-- 初始化命令 -->
openclaw onboard

<!-- 配置管理命令: -->
openclaw config <setting>：查看或修改当前配置。
openclaw reset <setting>：重置指定的设置。

<!-- 查看运行状态 -->
openclaw status
systemctl --user status openclaw-gateway.service 

<!-- 前台启动 -->
openclaw gateway

<!-- 后台启动 -->
openclaw gateway install（执行一次）
openclaw gateway start
<!-- 后台停止 -->
openclaw gateway stop
<!-- 重启服务 -->
openclaw gateway restart
<!-- 打开页面 -->
openclaw dashboard
<!-- 查看日志 -->
openclaw logs --follow
<!-- 升级 -->
openclaw update
<!-- 查看和设置模型 -->
openclaw models list
openclaw models set siliconflow/Pro/zai-org/GLM-4.7

<!-- 手动安装skill -->
npm config set registry https://registry.npmmirror.com
cd ~/.openclaw/workspace/skills
git clone https://ghproxy.com/https://github.com/6551Team/opentwitter-mcp.git
openclaw gateway restart

git clone https://ghproxy.com/https://github.com/vercel-labs/agent-browser
git clone https://github.com/vercel-labs/agent-browser
