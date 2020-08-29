
### re模块
- [x] :
- re.compile(pattern,flags=0)   
    - 功能：生成正则表达式对象
    - 参数：
        - pattern:正则表达式
        - flags:功能标志位，提供更丰富的筛选功能
    - 返回值：正则表达式对象
- re.findall(pattern,string,flags)
    - 功能：查找正则表达式匹配内容
    - 参数：
        - pattern：正则表达式
        - string： 目标字符串
        - flags：功能标志位
    - 返回值：
        -  将匹配到的内容放在一个列表返回；如果有子组，只能返回子组匹配到的内容
- regex.findall(string=None,post=0,endops=999)
    - 功能：查找正则表达式匹配内容
    - 参数：
        - string： 目标字符串
        - pos：匹配目标字符串的起始位置
        - endpos:匹配目标字符串的结束位置
    - 返回值：
        -  将匹配到的内容放在一个列表返回；如果有子组，只能返回子组匹配到的内容

    - 示例：
    ```
    import re
    p=r'(ab)cd(ef)'
    #使用re调用
    l=re.findall(p,'abcdef--abcdef')
    print(l)
    #使用正则对象调用
    regex=re.compile(p)
    l=regex.findall('abcdef--abcdef')
    print(l)
    
    regex=re.compile(p)
    l=regex.findall('abcdef--abcdef',0,7)
    print(l)
    输出：
    [('ab', 'ef'), ('ab', 'ef')]
    [('ab', 'ef'), ('ab', 'ef')]
    [('ab', 'ef')]
    ```

- re.split(pattern,string,flags=0)
    - 功能：通过正则表达式分隔目标字符串
    - 参数：
        - pattern：正则表达式
        - string：目标字符串
    - 返回值：返回分隔后的字符串列表
    - 示例：
    ```
    l=re.split(r'\s+','hello world \nnihao lulu')
    print(l)
    输出：
    ['hello', 'world', 'nihao', 'lulu']
    ```
- re.sub(pattern,replaceStr,string,max,flags)
    - 功能：替换正则表达式匹配到的内容
    - 参数：
        - pattern:
        - replaceStr:要替换的内容
        - string：目标字符串
        - max:最多替换几处
    - 返回值：返回替换后的字符串
    -  示例：
    ```
    l=re.sub(r'\s+',"##",'y z z ni hao')
    print(l)
    l=re.sub(r'\s+',"##",'y z z ni hao',1)
    print(l)
    输出：
    y##z##z##ni##hao
    y##z z ni hao
    ```

- re.subn(pattern,replaceStr,string,max,flags)
    - 功能：替换正则表达式匹配到的内容
    - 参数：
        - pattern:
        - replaceStr:要替换的内容
        - string：目标字符串
        - max:最多替换几处
    - 返回值：返回替换后的字符串和实际替换的个数
    -  示例：
    ```
    l=re.subn(r'\s+',"##",'y z z ni hao')
    print(l)
    l=re.subn(r'\s+',"##",'y z z ni hao',1)
    print(l)
    输出：
    ('y##z##z##ni##hao', 4)
    ('y##z z ni hao', 1)
    ```
- re.finditer(pattern,string,flags)
    -  功能：使用正则表达式匹配的内容
    -  参数：
        -  pattern正则表达式
        - string:目标字符串
    - 返回值：返回匹配到的内容的迭代器对象
    - 示例:
    ```
    import re 
    it=re.finditer(r'[A-Z]\w*','A good boy:Tom')
    #调用group()获取匹配内容
    for i in it:
        print(i.group())
    输出：
    A
    Tom
    ```
- re.fullmatch(pattern,string,flags)
    - 功能：完全匹配目标字符串
    - 参数：
        - pattern：正则表达式
        - string:目标字符串
    - 返回值：match对象；匹配不到返回None
    - 示例：
    ```
    #类似绝对匹配
    obj=re.fullmatch('\w*','abcdefg123')
    try:
        print(obj.group())
    except AttributeError:
        print('没有匹配到')
    ```

- re.match(pattern,string,flags)
    - 功能：完全匹配目标字符串的开头
    - 参数：
        - pattern：正则表达式
        - string:目标字符串
    - 返回值：match对象；匹配不到返回None
    - 示例：
    ```
    #类似在正则前加^
    obj=re.match(r'foo','Foo,food on the table')
    try:
        print(obj.group())
    except AttributeError:
        print('没有匹配到')  
    输出：
    没有匹配到
    
    obj=re.match(r'foo','food on the table')
    try:
        print(obj.group())
    except AttributeError:
        print('没有匹配到')
    输出：
    foo
    ```

- re.search(pattern,string,flags)
    - 功能：匹配目标字符串
    - 参数：
        - pattern：正则表达式
        - string:目标字符串
    - 返回值：match对象；只能匹配第一个；匹配不到返回None
    - 示例：
    ```
    obj=re.search(r'foo','The food on the table,foo')
    try:
        print(obj.group())
    except AttributeError:
        print('没有匹配到')
    ```
- **注意**：由于fullmatch,match,search函数匹配不到会返回None，而None没有match对象的属性，所以往往需要异常判断处理



#### 正则对象其他属性
- flags:标志位
- patrern:正则表达式
- groups:有多少个子组
- groupindex:捕获组形成的字典
    - 组名为键，第几组为值



# 作业
- 读取一个文本，将文本中，将文本中所有以大写字母开头的单词匹配出来
- 熟练元字符的使用
- 复习mysql


