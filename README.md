# xqdjymfh
QQ、微信防红链接生成器
一个基于 GitHub Pages 的 QQ、微信防红链接生成工具，利用 github.io 域名的天然防红特性，为用户提供安全可靠的链接中转服务。

🔒 密码保护系统
* 访问控制：默认密码为 taocrypt
* 会话管理：使用 sessionStorage 保存验证状态
* 安全验证：防止未授权访问
🎨 现代化用户界面
* 弹窗式设计：密码验证以模态框形式显示
* 背景模糊效果：使用 backdrop-filter 实现优雅的视觉层次
* 响应式布局：完美适配桌面端和移动端
* 动画效果：平滑的显示/隐藏过渡动画
🌐 智能环境检测
* QQ/微信内嵌：在社交应用内使用 iframe 内嵌显示
* 浏览器跳转：普通浏览器中直接跳转到目标网址
* 标题获取：自动获取目标网页标题并显示
📱 跨平台兼容
* 移动端优化：针对手机和平板设备优化
* 触摸友好：大按钮和清晰的触摸目标
* 自适应布局：根据屏幕尺寸自动调整

**🔧 部署说明**
静态项目，支持 GitHub Pages / Cloudflare Pages，不需要后端数据库
GitHub Pages 部署
① Fork 仓库
1. 打开 https://github.com/
2. 右上角点 Fork → 复制一份到你自己的 GitHub 账号下
3. Fork 完成后，进入你账号下的这个仓库
② 开启 GitHub Pages
1. 仓库上方：Settings（设置）
2. 往下滑找到 Pages
3. Source（来源）：选 main 分支，文件夹选 / (root) 根目录
4. 保存（Save）
5. 等 1～3 分钟部署，访问地址格式： https://你的github用户名.github.io/LinkPass
6. 在等几分钟会再自动部署出一个仓库项目，Code界面不显示Settings
index.html        # 主页（密码弹窗 + 链接生成清单）
api/index.html    # 中转页面
assets/           # css js 静态资源
images/           # 图片
LICENSE/README.md   #其他

## 修改访问密码
index.html；173行修改底部版权；194行修改访问密码

## 自定义域名
1. 还是 Pages 设置页，找到 Custom domain
2. 填入你的域名，例如 xqdj.site，保存
3. 去域名解析（Cloudflare / 阿里云）添加 CNAME；
4.  xqdj.site  CNAME  你的用户名.github.io
4. 等解析生效，之后可以用你自己域名访问
5. 前提是自定义域名没问题，不拦截不包红，否则生成的防红链接也一样打不开

## 🚀 使用方法
1. 访问网站
进入防红链接生成器：访问 https://你的用户名.github.io/仓库名
2. 输入密码
* 默认密码：taocrypt
* 支持回车键快速验证
* 验证成功后自动保存登录状态
3. 生成防红链接
* 在输入框中输入需要跳转的网址
* 点击"生成"按钮
* 复制生成的防红链接
4. 分享使用
* 将生成的链接分享到 QQ 或微信
* 链接会自动防红，用户可正常访问

### Cloudflare  部署
方式 1：Continue with GitHub（推荐✅） 直接关联你刚才的 Museumss/LinkPass 仓库，以后改代码提交到 GitHub，Cloudflare 会自动重新部署，不用反复上传文件。
1. 点 Continue with GitHub
2. 授权，然后选中 Museumss/LinkPass
3. 构建设置：
    * 构建命令：留空
    * 输出目录：留空
    * 根目录：/
4. 部署！
部署完会给一个 xxx.pages.dev 域名，之后可以绑定你自己的域名。
重点：部署好之后，JS 自动读取当前域名，生成防红链接，不用改代码！

方式 2：Upload your static files 下载整套源码压缩包，解压后，把里面所有文件直接拖进去上传（注意：不要套一层文件夹！！根目录直接是 index.html、api、assets、images，否则 404，自定义名称，其他默认），适合一次性上传，后续改源码要重新上传。

