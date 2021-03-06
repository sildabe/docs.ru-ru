---
title: "Функция Statement (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: af87477f81fab8406d726ebc8c81260b371d71c8
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="function-statement-visual-basic"></a>Оператор Function (Visual Basic)
Объявляет имя, параметры и код, определяющие `Function` процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательный. В разделе [список атрибутов](attribute-list.md).  
  
-   `accessmodifier`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательный. В разделе [общего](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [тени](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Необязательный. В разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Необязательный. В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Обязательный. Имя процедуры. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Необязательный. Список параметров типа для универсальной процедуры. В разделе [введите список](type-list.md).  
  
-   `parameterlist`  
  
     Необязательный. Список имен локальных переменных, представляющих параметры этой процедуры. В разделе [список параметров](parameter-list.md).  
  
-   `returntype`  
  
     Обязателен, если `Option Strict` — `On`. Тип данных значения, возвращаемые этой процедурой.  
  
-   `Implements`  
  
     Необязательный. Указывает, что эта процедура реализует один или несколько `Function` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. В разделе [реализует оператор](implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Function`.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание|  
    |---|---|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого данной процедурой, содержащей класс или структуру.|  
    |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|  
  
-   `Handles`  
  
     Необязательный. Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий. В разделе [обрабатывает](handles-clause.md).  
  
-   `eventlist`  
  
     Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает данная процедура.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.  
  
     `eventvariable.event`  
  
    |Отделение|Описание|  
    |---|---|  
    |`eventvariable`|Обязательный. Объектная переменная объявлена с типом данных класса или структуры, который вызывает событие.|  
    |`event`|Обязательный. Имя события, которое обрабатывает данная процедура.|  
  
-   `statements`  
  
     Необязательный. Блок операторов для выполнения этой процедуры.  
  
-   `End Function`  
  
     Завершает определение данной процедуры.  
  
## <a name="remarks"></a>Примечания  
 Весь исполняемый код должен быть внутри процедуры. Каждая процедура в свою очередь, объявляется внутри класса, структуры или модуль, который называется содержащего класса, структуры или модуля.  
  
 Для возврата значения в вызывающий код, используйте `Function` процедуры; в противном случае, используйте `Sub` процедуры.  
  
## <a name="defining-a-function"></a>Определение функции  
 Можно определить `Function` процедуры только на уровне модуля. Таким образом контекст объявления функции должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).  
  
 `Function`процедуры по умолчанию для общего доступа. Можно настроить их уровни доступа с помощью модификаторов доступа.  
  
 A `Function` процедура может объявить тип данных, процедура возвращает значение. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса. Если не указать `returntype` , процедура возвращает `Object`.  
  
 Если эта процедура использует `Implements` ключевое слово, содержащего класса или структуры, необходимо также иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Function` (в `definedname`) не должны совпадать с именем данной процедуры (в `name`).  
  
> [!NOTE]
>  Лямбда-выражения можно использовать для определения встроенной функции выражения. Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Возврат из функции  
 Когда `Function` процедура возвращает вызывающему коду, выполнение продолжается с оператора, следующего за оператором, который вызвал процедуру.  
  
 Для возврата значения из функции, можно присвоить значение имени функции или включить ее в `Return` инструкции.  
  
 `Return` Инструкция одновременно назначает возвращаемое значение и выходит из функции, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements&#24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем использует `Exit Function` инструкции.  
  
 [!code-vb[VbVbalrStatements&#23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 `Exit Function` И `Return` инструкции вызывают Немедленный выход из `Function` процедуры. Любое число `Exit Function` и `Return` операторы могут использоваться в любом месте в процедуре, и можно смешивать `Exit Function` и `Return` инструкции.  
  
 Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, который указан в `returntype`. Если `returntype` не указан, процедура возвращает `Nothing`, которое является значением по умолчанию для `Object`.  
  
## <a name="calling-a-function"></a>Вызов функции  
 Можно вызвать `Function` процедуры с помощью имени процедуры, за которым следует список аргументов в круглые скобки в выражении. Скобки могут опускаться только в том случае, если вы не имеет аргументов. Тем не менее код является более удобочитаемым, если всегда включать круглые скобки.  
  
 Можно вызвать `Function` процедуры, такие как функции так же, что вызывать любую библиотеку `Sqrt`, `Cos`, или `ChrW`.  
  
 Можно также вызвать функцию с помощью `Call` ключевое слово. В этом случае возвращаемое значение обрабатывается. Использование `Call` ключевое слово не рекомендуется в большинстве случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).  
  
 Visual Basic иногда переупорядочивает арифметические выражения для повышения внутренней эффективности. По этой причине не следует использовать `Function` процедуру в арифметическом выражении при изменении функции значения переменных в одном выражении.  
  
## <a name="async-functions"></a>Асинхронные функции  
 *Async* позволяет вызывать асинхронные функции без использования явных обратных вызовов или вручную разделения кода между несколькими функции или лямбда-выражения.  
  
 Если пометить функцию с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в функции. Если управление достигает `Await` выражения в `Async` функции, управление возвращается вызывающему объекту и ход выполнения в функции приостанавливается до завершения выполнения ожидаемой задачи. После завершения задачи в функции можно возобновить выполнение.  
  
> [!NOTE]
>  `Async` Процедура возвращает вызывающему объекту, когда либо он встречает первый ожидаемый объект, который еще не завершена, или он доходит до конца `Async` процедура, что произойдет раньше.  
  
 `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601>или <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Пример `Async` функции с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>приведен ниже.</xref:System.Threading.Tasks.Task%601>  
  
 `Async` Функция не может объявить все [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.  
  
 Объект [оператор Sub](sub-statement.md) также могут быть помечены с помощью `Async` модификатор. В основном используется для обработчиков событий, где значение не может быть возвращен. `Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедура не может перехватывать исключения, возникающие с `Sub` процедуры.  
  
 Дополнительные сведения о `Async` функции, в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [Async возвращают типы](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Функции итераторов  
 *Итератор* функция выполняет настраиваемую итерацию по коллекции, например, список или массив. Использует функции итератора [Yield](yield-statement.md) инструкции для возврата каждого элемента одному за раз. Когда [Yield](yield-statement.md) оператору запоминается текущее расположение в коде. Выполнение возобновляется с этого места при очередном вызове функции итератора.  
  
 Вызвать итератор из клиентского кода с помощью [For Each... Далее](for-each-next-statement.md) инструкции.  
  
 Возвращаемый тип функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
 Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Function` инструкции для объявления имени, параметров и кода, образующих текст `Function` процедуры. `ParamArray` Модификатор разрешает функции принимать переменное число аргументов.  
  
 [!code-vb[VbVbalrStatements&#25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается функция, объявленная в предыдущем примере.  
  
 [!code-vb[VbVbalrStatements&#26;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` имеет инструкцию `Return`, которая возвращает целое число. Поэтому объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` возвращает целое число. Это показано в этом операторе: `Dim result As Integer = Await delayTask`.  
  
 `startButton_Click` Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должен ожидать, как показано в следующей инструкции: `Await DoSomethingAsync()`. `startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.  
  
 [!code-vb[csAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Sub](sub-statement.md)   
 [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Список параметров](parameter-list.md)   
 [Оператор Dim](dim-statement.md)   
 [Оператор Call](call-statement.md)   
 [Предложение Of (Visual Basic)](of-clause.md)   
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Практическое руководство: использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Выражение функции](../../../visual-basic/language-reference/operators/function-expression.md)

