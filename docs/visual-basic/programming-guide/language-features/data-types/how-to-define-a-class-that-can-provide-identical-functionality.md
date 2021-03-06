---
title: "Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "аргументы типа данных, использование"
  - "параметры типа, определение"
  - "аргументы типа данных, определение"
  - "аргументы [Visual Basic], типы данных"
  - "ключевого слова, использование"
  - "ограничения, универсальные типы в Visual Basic"
  - "универсальные параметры"
  - "параметры типа данных"
  - "параметры типа данных, использование"
  - "универсальные шаблоны [Visual Basic], определение классов при помощи параметров типа"
  - "типы данных [Visual Basic], в качестве параметров"
  - "типы данных [Visual Basic], в качестве аргументов"
  - "параметры, типы"
  - "аргументы типа"
  - "типы [Visual Basic], универсальные"
  - "параметры, универсальные"
  - "параметры типа"
  - "аргументы типа данных"
  - "параметры, тип данных"
  - "универсальные шаблоны [Visual Basic], определение универсальных типов"
  - "параметры типа данных, определение"
  - "аргументы типа, определение"
  - "аргументы [Visual Basic], тип"
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Можно определить класс, из которого можно создавать объекты, обеспечивающие одинаковые функциональные возможности для различных типов данных. Для этого укажите в определении один или несколько *параметров типа*. После этого класс может служить шаблоном для объектов, которые используют различные типы данных. Класс, определенный таким образом, называется *универсальным классом*.  
  
 Преимущество определения универсального класса состоит в том, он определяется только один раз, и код может использовать его для создания многих объектов, использующих разнообразные типы данных. Это дает более высокую производительность, чем при определении класса с помощью типа `Object`.  
  
 Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.  
  
### Определение класса с помощью параметра типа  
  
1.  Определите класс обычным способом.  
  
2.  Добавьте `(Of` *typeparameter*`)` сразу после имени класса для указания параметра типа.  
  
3.  Если имеется более одного параметра типа, создайте разделенный запятыми список, заключенный в круглые скобки. Не следует повторять ключевое слово `Of`.  
  
4.  Если код выполняет с параметром типа какие\-либо операции, отличные от простого присваивания, следует записать данный параметр типа с условием `As` для добавления одного или нескольких *ограничений*. Ограничение гарантирует, что тип, указанный для данного параметра типа, удовлетворяет определенным требованиям:  
  
    -   Поддерживает операции, например `>`, которые выполняются кодом.  
  
    -   Поддерживает элементы, например методы, к которым обращается код.  
  
    -   Предоставляет конструктор без параметров.  
  
     Если не указаны никакие ограничения, код сможет использовать только операции и элементы, поддерживаемые [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). Дополнительные сведения см. в разделе [Список типов](../../../../visual-basic/language-reference/statements/type-list.md).  
  
5.  Определите все элементы класса, объявляемые с помощью указанного типа, и объявите их `As` `typeparameter`.  Это относится к внутреннему хранилищу, параметрам процедур и возвращаемым значениям.  
  
6.  Убедитесь, что код использует только операции и методы, поддерживаемые типом данных, который может быть предоставлен для `itemType`.  
  
     В следующем примере определяется класс, управляющий простым списком. Он хранит список во внутреннем массиве `items`, и использующий код может объявить тип данных элементов списка. Параметризованный конструктор позволяет использующему коду задать значение верхней границы `items`, и конструктор по умолчанию устанавливает это значение равным 9 \(для всех 10 элементов\).  
  
     [!code-vb[VbVbalrDataTypes#7](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_1.vb)]  
  
     Можно объявить один класс из `simpleList` для хранения списка значений `Integer`, другой класс — для хранения списка значений `String` и еще один — для хранения значений `Date`. Кроме типа данных элементов списка, объекты, созданные из всех этих классов, ведут себя одинаково.  
  
     Аргумент типа, который использующий код указывает для `itemType`, может быть встроенным типом, например `Boolean` или `Double`, структурой, перечислением или любым типом класса, включая определяемый приложением.  
  
     Можно протестировать класс `simpleList` с помощью следующего кода.  
  
     [!code-vb[VbVbalrDataTypes#8](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-define-a-class-that-can-provide-identical-functionality_2.vb)]  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Список типов](../../../../visual-basic/language-reference/statements/type-list.md)   
 [Практическое руководство. Использование универсального класса](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)