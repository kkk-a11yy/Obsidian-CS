# 安装node

```r
nvm -v
	0.39.4

nvm ls-remote

nvm use 14.0.0
	Now using node v14.0.0 (npm v6.14.4)

nvm alias default 14
	default -> 14 (-> v14.0.0)

node -v
	v14.0.0

npm -v
	6.14.4

```
# 安装cnpm

```r
npm install cnpm -g --registry=https://registry.npm.taobao.org
	/Users/ksia/.nvm/versions/node/v14.0.0/bin/cnpm -> /Users/ksia/.nvm/versions/node/v14.0.0/lib/node_modules/cnpm/bin/cnpm
	+ cnpm@9.2.0
	added 675 packages from 187 contributors in 24.611s

vim ~/.bash_profile
	//输入下面的
	export export CNPM_HOME=/Users/ksia/.nvm/versions/node/v14.0.0/lib/node_modules/cnpm/bin/cnpm
	export PATH=$PATH:$CNPM_HOME/bin

//刷新
source ~/.bash_profile

//查看cnpm 版本
cnpm -v
	internal/modules/cjs/loader.js:1017
	  throw err;
	  ^
	
	Error: Cannot find module 'node:util'
	Require stack:
	- /Users/ksia/.nvm/versions/node/v14.0.0/lib/node_modules/cnpm/bin/cnpm
	    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:1014:15)
	    at Function.Module._load (internal/modules/cjs/loader.js:884:27)
	    at Module.require (internal/modules/cjs/loader.js:1074:19)
	    at require (internal/modules/cjs/helpers.js:72:18)
	    at Object.<anonymous> (/Users/ksia/.nvm/versions/node/v14.0.0/lib/node_modules/cnpm/bin/cnpm:3:15)
	    at Module._compile (internal/modules/cjs/loader.js:1185:30)
	    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1205:10)
	    at Module.load (internal/modules/cjs/loader.js:1034:32)
	    at Function.Module._load (internal/modules/cjs/loader.js:923:14)
	    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12) {
	  code: 'MODULE_NOT_FOUND',
	  requireStack: [
	    '/Users/ksia/.nvm/versions/node/v14.0.0/lib/node_modules/cnpm/bin/cnpm'
	  ]
	}
```