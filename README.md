# OSS + CDN 自建图床

本图床供[个人博客](https://www.pil0txia.com)使用。

`PicGo`设定的自定义域名为`https://static.pil0txia.com`

本仓库为 Netlify 备用分流线路，域名`nl.static.pil0txia.com`

git config 中需禁用软链接（即`core.symlinks = false`），以确保 Git 仓库中通过符号链接同步的目录以文件形式上传。

对于新克隆的仓库，需要删除除 README.md 以外的所有文件，并从本地添加目录连接点和符号链接。

