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
