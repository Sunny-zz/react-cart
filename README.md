## 如何将 react 项目部署到 github 的 gh-pages 分支

### 方案一

- 验证我们的项目在 npm start 环境下可以正常运行
- package.json 内添加 homapage: "http://Sunny-zz.github.io/react-cart"
- 网上新建仓库将我们的项目传到网上
- 本地新建 gh-pages 分支
- 切换到 gh-pages 分支，执行 npm run build 然后将里面的所有内容删除 只留下 .git .gitignore 以及 build 文件夹下的所有内容(不需要 build 文件夹)
- 然后 git 三步 更新 gh-pages
- 最后到 http://Sunny-zz.github.io/react-cart 就可以访问项目了

**如果 homepage 填写错误，想要更改的话，需要先到 mster 分支更新 package.json 的 homepage，然后执行 npm run build 将 build 内的 文件拷贝，再然后切换到 gh-pages 分支，将拷贝的内容粘贴到这里。最后更新 gh-pages 分支。**

### 方案二

- 验证我们的项目在 npm start 环境下可以正常运行
- package.json 内添加 homapage: "http://Sunny-zz.github.io/react-cart"
- 安装 gh-pages 包 `npm i -D gh-pages`
- 在 package.json 中的 script 字段下添加
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
- 网上新建仓库将我们的项目传到网上
- 执行 npm run deploy
- 最后到 http://Sunny-zz.github.io/react-cart 就可以访问项目了


## 将 react 项目部署到 netlify 免费服务器
- 将我们的项目上传到 github 仓库
- 到 netlify 网站上点击 New sit from Git，选择 GItHub，点击你要部署的仓库名
- Branch to Deploy 选择 master 分支，Build command 填写  npm run build ,Publish directory 填写 build/
- 最后点击 Deploy site ，在弹出的页面等待几分钟就部署成功了。
