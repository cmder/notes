### 官方文档

https://code.visualstudio.com/docs/languages/cpp

https://code.visualstudio.com/docs/cpp/config-mingw

https://code.visualstudio.com/docs/cpp/c-cpp-properties-schema-reference

### 关键点

VSCode作为一个编译器，要用来开发C++需要配套的C++开发环境。进行编程的环境需要能进行Build和Debug。围绕这些需求在使用层需要三个放置在.vscode文件夹下的配置文件：

- task.json 对应 Build
- launch.json 对应 Debug
- c_cpp_properties.json 用来配置语言本身的属性，比如C/C++的版本

### Build

点击Terminal—>Run Build Task可以直接运行

点击Terminal—>Configure Default Build Task可以编辑默认的task.json文件

### Debug

F5可直接Debug，生成文件launch.json，可加breakpoint，watch

### 配置C++属性

Ctrl+Shift+P 打开命令窗口—>C/C++:Edit Configures(UI)，可通过UI对c_cpp_properties.json文件进行修改