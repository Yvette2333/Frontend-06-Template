学习笔记

## LL构建AST算法

四则运算分析
- TokenNumber  [1-9]
- Operator: + - * / 
- Whitespace: <SP>
- LineTerminator: <LF><CR>

语法定义
```
// 运算表达式
<Expression>:: = 
  <AdditiveExpression><EOF>

// （加法表达式）
 <AdditiveExpression>:: =
  <MultiplicativeExpression>
  | <AdditiveExpression><+><MultiplicativeExpression>
  | <AdditiveExpression><-><MultiplicativeExpression>

// （乘法表达式）
  <MultiplicativeExpression>:: =
   <Number>
   | <MultiplicativeExpression><*><Number>
   | <MultiplicativeExpression></><Number>
```

终结符（基础运算符）： <EOF><Number><*></><+><->
非终结符（由基础运算符组合而成/非终结符的组合）： <AdditiveExpression><MultiplicativeExpression>

加减乘除有优先级处理
加法： 左右两个乘除表达式链接  /


### Regexp
Regexp.lastIndex
lastIndex 是正则表达式的一个可读可写的整型属性，用来指定下一次匹配的起始索引。

只有正则表达式使用了表示全局检索的 "g" 标志时，该属性才会起作用。此时应用下面的规则：

