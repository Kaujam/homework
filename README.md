# 测试文件
```
test_apk.py：测试 APK 类的功能，如提取包名、版本号、权限、活动等元数据，验证 APK 的签名信息等
test_analysis.py：测试分析模块，包括构建类和方法的调用图、分析方法的引用和实现关系、检测接口实现和继承结构等
test_axml.py：测试 AXML 解析功能，处理命名空间和属性，验证资源 ID 的解析和映射
test_dex.py：测试 DEX 文件的解析和分析功能，处理指令集和操作码，验证 DEX 文件的完整性和一致性
test_decompiler.py：测试反编译功能，验证 DEX 字节码到可读代码的转换，处理控制流图的生成
test_arsc.py：测试 resources.arsc 文件的解析功能，如提取应用名称和图标资源、处理多语言和多分辨率资源、验证资源 ID 与名称的映射关系
test_session.py：测试 Session 会话管理功能，包括添加和管理多个 APK 或 DEX 文件，保存和加载分析会话，验证会话中对象的完整性和一致性
```

# 使用 Androguard 进行 APK 分析
```
from androguard.misc import AnalyzeAPK

apk_path = "path/my.apk"
a, d, dx = AnalyzeAPK(apk_path)

print("Package Name:", a.get_package())  # 提取包名
print("Permissions:", a.get_permissions())  # 提取权限
print("App Name:", a.get_app_name())  # 提取应用名称
print("Main Activity:", a.get_main_activity())  # 提取主活动
```

# 使用 Session 管理多个 APK
```
from androguard.misc import Session

s = Session()
digest = s.add("path/my.apk")

a, d, dx = s.get_objects_apk(digest=digest)  # 获取分析对象
print("Package Name:", a.get_package())  # 提取包名
```
