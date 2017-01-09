### vscode中使用eslint
添加 
`"eslint": "^3.11.1",  
 "eslint-config-standard": "^6.2.1", 
 "eslint-plugin-promise": "^3.4.0", 
 "eslint-plugin-standard": "^2.0.1", `到package.json里面的devDependencies（如果用react,加上eslint-plugin-react）
 然后一定要reopen
####注：
 如果eslint不生效，重新打开项目，看看output里面的报错
