# fastlane安装教程

## 安装gym 
``` 
xcode-select —install 

ruby -v // 查看为2.0以上 

sudo gem install fastlane 
sudo gem install -n /usr/local/bin fastlane
```

## 总体步骤 
安装 xcode tool  
``` 
brew install xctool 
```

2. 使用命令： xcode-select --install  
3. 安装了 xcode tool 后  
4. 确定 ruby 版本在 2.0 以上  
5. 使用命令 :ruby -v  
6. 确定 ruby 版本后  
7. 安装 fastlane  
8. 使用命令： sudo gem install fastlane -NV  
9. 安装好 fastlane 后 

## 脚本的步骤{工作流程} 
1. 清理项目  
2. 生成 archive  
3. 导出 ipa  
4. 上传到 fir 

## 安装失败原因查看 
* https://www.pgyer.com/doc/view/ios_install_failed 
* [官方安装链接](https://docs.fastlane.tools/getting-started/ios/beta-deployment/)