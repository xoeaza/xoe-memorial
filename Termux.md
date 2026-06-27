pkg install git
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
cat ~/.ssh/id_rsa.pub | clip

cd ~/storage/shared/Download   # 或你想要的目录
git clone https://github.com/用户名/仓库名.git

<!-- 把克隆下来的文件夹移到非root能访问的目录下 -->
termux-setup-storage   # 首次运行授权
cp -r ~/your-repo ~/storage/shared/Download/