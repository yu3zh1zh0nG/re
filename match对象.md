# match对象的使用.

### match对象属性变量
- pos:
    - 目标字符串的开头位置
- endpos：
    - 目标字符串结束位置
- re：
    - 正则表达式对象
- string ：
    - 目标字符串
- lastgroup：
    - 最后一组名字
- lastindex：
    - 最后一组是第几组
-  示例：
```
#演示match对象
import re
regex=re.compile(r'(ab)cd(?P<dog>ef)')
mac=regex.search('abcdefghijk')

#匹配目标字符串起始位置
print(mac.pos)
print(mac.endpos)

#正则表达式对象和目标字符串
print(mac.re)
print(mac.string)

#最后一组名字和最后一组是第几组
print(mac.lastgroup)
print(mac.lastindex)
```








### match对象属性方法
- start()
    - 获取匹配到的内容的开始位置
- end()
    - 获取匹配到的内容的结束位置
- span()
    - 获取匹配到的内容的起始位置
- group(n=0)
    - 功能：获取match对象对应匹配到的内容
    - 参数：默认为0，表示获取正则表达式整体的匹配内容；如果赋值1，2，3..则表示获取某个子组的匹配内容
    - 返回值：返回匹配字符串
- groups()
    - 获取所有子组匹配 内容
- groupdict()
    - 将所有捕获组内容形成一个字典(只捕获有名字的：组名为键，子组为值)



















































































