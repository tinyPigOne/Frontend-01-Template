第二周学习总结
# 编程语言通识
##  分类
*  非形式语言
   *   中文
   *   英文
   *   其他
* 形式语言（乔姆斯基谱系）
  * 0型（无限制文法）
  * 1型（上下文相关文法）
  * 2型（上下文无关文法）
  * 3型（正则文法）
## 巴克斯范式（BNF)
    是一种用于表示上下文无关文法的语言, 上下文无关文法描述了一类形式语言.
 ### 产生式
 #### 简介
    BNF 规定是推到规则(产生式)的集合, 写为:

    <符号>::=<使用符号的表达式>

    这里的<符号>是非终结符, 而表达式由一个符号序列, 或勇表示选择的竖杠 '|'分隔的多个符号序列构成, 每个符号序列整体都是左端的符号的一种可能的替代. 从未在末端出现的符号叫做终结符
#### 规则
* 用尖括号括起来的名称来表示语法结构名
* 语法结构分成基础结构和需要用其他语法结构定义的复用结构
  *  基础结构称终结符
  *  复合结构称非终结符
* 引号和中间的字符表示终结符
* 可以有括号
* 表示重复多次
* | 表示或
* 表示至少一次
* 四则运算:
  *  1 + 2 * 3
* 终结符:
  * Number
  *  +-*/
  * ...
* 非终结符
  * MulitiplicativeExpression
  * AddtiveExpression
  * ...
## 现代语言的识别
* C++中, *可能表示乘号或者指针, 具体是哪个, 取决于星号前面的标识符是否被声明为类型
* VB中, < 可能是小于号, 也可能是XML直接量的开始, 取决于当前位置是否可以接受XML直接量
* JavaScript中, / 可能是除号, 也可能是正则表达式的开头, 处理方式类似于VB, 字符串模板中也需要特殊处理}, 还有自动插入分好规则
## 图灵完备性
* 命令式-图灵机
  *  goto
  *  if和while
*  声明式
   * 递归
## 动态静态
* 动态
  * 在用户的设备/在线服务器上
  * 产品实际运行时
  * runtime
* 静态
  * 在程序员的设备上
  * 产品开发时
  * compiletime
## 类型系统
* 动态类型系统和静态类型系统
* 强类型和弱类型
* 复合类型
  * 结构体
  * 函数签名
* 子类型
  * 逆变
  * 协变
## 由原子到程序
* Atom
   * Identifier
   * Literal
* Expression
    * Atom
    * Operator
    * Punctuator
* Statement
    * Expression
    * Keyword
* Structure
    * Function
    * Class
    * Process
    * Namespace
* Program
    * Program
    * Module
    * Package
    * Library
## Atom Identifier & Literal
* WhiteSpace
    * \<TAB>：\t
    * \<VT>： \v
    * \<FF>：\f
    * \<SP>：\s
    * \<NBSP>：NO-BREAK SPACE
    * \<ZWNBSP>：ZERO WIDTH NO-BREAK SPACE
    * \<USP>
* LineTerminator
    * \<LF>：\n
    * \<CR>：\r
    * \<LS>
    * \<PS>
* Comment
    * // comment
    *   /* comment */
* CommonToken
    *  IdentifierName
    *  Punctuator
    *  NumericLiteral
    *  StringLiteral
    *  Template
## JS基本类型Type
* Number
  * 浮点数比较: Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON
* String
  * 支持码点: U+0000 ~ U+10FFFF， 但推荐只使用 U+0000 ~ U+FFFF （BMP）
    *   UCS-2 用 2 个字节表示 BMP 的码点
    *   UCS-4 用 4 个字节表示码点`'\u{10000}'.length // 2`
        *   坑 1：length 属性和split 方法。解决`：Array.from(strings)`
        *   坑 2：码点与字符互转。解决：使用CodePoint的Api
        *   坑 3：正则匹配。解决：`/./u`
  * 存储方式：UTF8/UTF16
* Boolean
* Null
* Undefined
* Symbol
