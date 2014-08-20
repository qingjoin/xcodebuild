首先进入到工程文件所在的目录。比如我的文件某个工程放在(.xcodeproj文件所在的目录) /Users/xxx/xxx

然后cd /Users/xxx/xxx 到这个目录下

##第一步先编译生成testDemo.xcarchive 文件。 

 xcodebuild -archivePath "testDemo.xcarchive" -project PcAppleSdkDemo.xcodeproj -sdk iphoneos  -scheme "PcAppleSdkDemo" -configuration "Release Adhoc" archive

//这里生成的testDemo.xcarchive文件目录与.xcodeproj是同一目录

//-archivePath  生成的.xcarchive 名字

//-project   目标文件名

//-scheme  项目的目标文件名 

 

##第二步把生成的testDemo.xcarchive文件打包成ipa 格式。 

 xcodebuild -exportArchive -exportFormat IPA -exportProvisioningProfile "qingyunDeveloper" -archivePath "testDemo.xcarchive" -exportPath "testDemo.ipa"

成功后显示

** EXPORT SUCCEEDED **

//这时的ipa 文件存放目录与.xcodeproj是同一目录

//-exportProvisioningProfile 这个是选择的证书   你的证书名是什么这里就填写什么。


//参考资料 ： http://minhdanh2002.blogspot.jp/2014/06/archiving-ios-projects-from-command.html
