# translate_app
这是一个使用Flutter开发的简单翻译app，支持在 iOS Simulator 和 macOS Simulator
上运行，通过 HTTP 调用后端翻译接口。

## 功能说明

- 中文输入框
- 点击按钮触发翻译
- 显示英文翻译结果
- 显示关键词列表
- 支持 loading 状态
- 支持 iOS Simulator 与 macOS 运行

## 本地运行步骤
1. 克隆项目
git clone [<](https://github.com/tian88888888/translate-app.git)>
cd <translate-app>

2. 安装依赖
flutter pub get

3. 用iOS Simulator，无法访问127.0.0.1，使用本机局域网IP
检查flutter devices里有没有iOS，如果没有，终端输入：
open -a Simulator
如果没有手机弹出来
- 彻底关闭Simulator：
killall Simulator || true
- 重启Simulator服务
sudo killall -9 com.apple.CoreSimulator.CoreSimulatorService || true
- 重新打开

-启动服务
flutter run --dart-define=API_BASE_URL=http://192.168.x.x:8000（局域网ip）

4. 用macOS
flutter run -d macos --dart-define=API_BASE_URL=http://127.0.0.1:8000
需要在 Xcode 中开启 App Sandbox 的 Outgoing Connections (Client) 权限