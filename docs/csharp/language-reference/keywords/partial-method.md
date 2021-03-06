---
title: "разделяемый (метод) (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "partialmethod_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "разделяемые методы [C#]"
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# разделяемый (метод) (Справочник по C#)
Сигнатура разделяемого метода определяется в одной части разделяемого типа, а реализация определяется в другой части типа.  Разделяемые методы позволяют конструкторам классов предоставлять ловушки методов \(аналогичные обработчикам событий\), которые при необходимости могут быть реализованы разработчиками.  Если реализация не предоставлена разработчиком, компилятор удаляет сигнатуру во время компиляции.  К разделяемым методам применяются следующие условия.  
  
-   Сигнатуры в обеих частях разделяемого типа должны совпадать.  
  
-   Метод должен возвращать значение void.  
  
-   Отсутствуют модификаторы доступа не допускаются.  Разделяемые методы неявно являются закрытыми.  
  
 В приведенном ниже примере показан разделяемый метод, определенный в двух частях разделяемого класса.  
  
 [!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Для получения дополнительной информации см. [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [partial \(тип\)](../../../csharp/language-reference/keywords/partial-type.md)