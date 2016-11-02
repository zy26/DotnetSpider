# RegexFormatter
正则格式化器。作为Attribute附加在属性前，利用正则表达式将PropertySelector提取出的内容进一步加工，
参数列表：

### Pattern

string 类型，正则表达式，匹配成功后，Formattter处理后的属性值就是匹配值，匹配失败并不会修改传入Formattterr的属性值

example: 

    [RegexFormatter(Pattern = @"\w+")]

In: "this is a sample",Out:"this"

In: "2016 11 02",Out:"2016 11 02"

### True

string 类型，若设置了这个属性值，当正则匹配成功后，Formattter处理后的属性值就是Ture属性的值

example: 

    [RegexFormatter(Pattern = @"\w+", True ="match success!")]

In: "this is a sample",Out:"match success!"

In: "2016 11 02",Out:"2016 11 02"

### False

string 类型，若设置了这个属性值，当正则匹配失败后，Formattter处理后的属性值就是False属性值

example: 

    [RegexFormatter(Pattern = @"\w+", True ="match success!",False ="match failed!")]

In: "this is a sample",Out:"match success!"

In: "2016 11 02",Out:"match failed!"

### Group

int Group //正则表达式匹配分组，若设置了该值，当正则匹配成功后，返回匹配分组的结果。example: 

    [RegexFormatter(Pattern = @"\w+ (\w+) \w+ (\w+)",Group = 0)]

In: "this is a sample",Out:"this is a sample"

    [RegexFormatter(Pattern = @"\w+ (\w+) \w+ (\w+)",Group = 1)]

In: "this is a sample",Out:"is"

    [RegexFormatter(Pattern = @"\w+ (\w+) \w+ (\w+)",Group = 2)]

In: "this is a sample",Out:"sample"
