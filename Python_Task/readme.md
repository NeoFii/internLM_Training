# Python Task
### 任务一
请实现一个wordcount函数，统计英文字符串中每个单词出现的次数。返回一个字典，key为单词，value为对应单词出现的次数。
Eg:

Input:

```python
"""Hello world!  
This is an example.  
Word count is fun.  
Is it fun to count words?  
Yes, it is fun!"""
```

Output:

```python
{'hello': 1,'world!': 1,'this': 1,'is': 3,'an': 1,'example': 1,'word': 1, 
'count': 2,'fun': 1,'Is': 1,'it': 2,'to': 1,'words': 1,'Yes': 1,'fun': 1  }
```

TIPS：记得先去掉标点符号,然后把每个单词转换成小写。不需要考虑特别多的标点符号，只需要考虑实例输入中存在的就可以。

```python
text = """
Got this panda plush toy for my daughter's birthday,
who loves it and takes it everywhere. It's soft and
super cute, and its face has a friendly look. It's
a bit small for what I paid though. I think there
might be other options that are bigger for the
same price. It arrived a day earlier than expected,
so I got to play with it myself before I gave it
to her.
"""

def wordcount(text):
    pass

```

代码：
```python
text = '''
Got this panda plush toy for my daughter's birthday,
who loves it and takes it everywhere. It's soft and
super cute, and its face has a friendly look. It's
a bit small for what I paid though. I think there
might be other options that are bigger for the
same price. It arrived a day earlier than expected,
so I got to play with it myself before I gave it
to her.
'''


def wordcount(text):
    punctuations = [',', '.', '!', '?', ';', ':', '-', "'"]
    for i in punctuations:
        text = text.replace(i, '')
    new_text = text.lower().split()
    words = {}
    for word in new_text:
        if word in words:
            words[word] += 1
        else:
            words[word] = 1
    return words


print(wordcount(text))
```

运行结果：
```python
{'got': 2, 'this': 1, 'panda': 1, 'plush': 1, 'toy': 1, 'for': 3, 'my': 1, 'daughters': 1, 'birthday': 1, 'who': 1, 'loves': 1, 'it': 5, 'and': 3, 'takes': 1, 'everywhere': 1, 'its': 3, 'soft': 1, 'super': 1, 'cute': 1, 'face': 1, 'has': 1, 'a': 3, 'friendly': 1, 'look': 1, 'bit': 1, 'small': 1, 'what': 1, 'i': 4, 'paid': 1, 'though': 1, 'think': 1, 'there': 1, 'might': 1, 'be': 1, 'other': 1, 'options': 1, 'that': 1, 'are': 1, 'bigger': 1, 'the': 1, 'same': 1, 'price': 1, 'arrived': 1, 'day': 1, 'earlier': 1, 'than': 1, 'expected': 1, 'so': 1, 'to': 2, 'play': 1, 'with': 1, 'myself': 1, 'before': 1, 'gave': 1, 'her': 1}
```

### 任务二
请使用本地vscode连接远程开发机，将上面你写的wordcount函数在开发机上进行debug，体验debug的全流程，并完成一份debug笔记(需要截图)。

首先使用VSCode连接远端开发机，在根目录下创建wordcount.py文件，将任务一代码粘贴。

设置好断点，然后选择python debug:使用lanuch.json进行调试

![pic1](./pics/1.png)

选择Python Debugger，注意：这里需要在扩展中下载对应的包

![pic2](./pics/2.png)

顶部有继续、逐过程、单步调试、结束等按钮，选择相应的按钮执行即可。同时左侧出现变量栏中有程序的全局变量和局部变量，调用的堆栈等。

![pic3](./pics/3.png)

调试完成后会生成程序结果

![pic4](./pics/4.png)

debug完成后会在当前目录下生成.vscode文件夹，在该文件夹下生成一个json配置文件。

![pic5](./pics/5.png)