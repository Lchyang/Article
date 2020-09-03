# vscode vue eslint 配置踩坑
问题主要是由于初始化项目的时候没有手动配置添加eslint相关依赖导致配置没有生效
在cli3中eslint 的主要配置存在于package.json中
如果手动下载的安装包没有生效，可以在vscode 中寻找create eslint configation file 命里运行 或者在命令行里面运行node_modules/.bin/eslint --init