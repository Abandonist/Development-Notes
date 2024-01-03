## 安装
```pip install line_profiler```
## 使用
1. 在函数定义前加入 @profile：
   ```
   @profile
   def test():
     pass
   ```
2. 执行以下命令查看各行代码效率：
   ```
   kernprof -l -v scatter.py  # -v 表示打印输出，删除会在命令执行路径下生成.lprof文件
   python -m line_profiler script_to_profile.py.lprof  # 用以查看.lprof文件
   ```
##参考链接
https://github.com/pyutils/line_profiler
