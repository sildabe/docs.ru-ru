---
title: "Предложение Handles (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Handles
- vb.Handles
dev_langs:
- VB
helpviewer_keywords:
- Handles keyword
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
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
ms.openlocfilehash: 7c79935e7f15f31abca7efddbc443239d5db2f58
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="handles-clause-visual-basic"></a>Предложение Handles (Visual Basic)
Заявляет, что процедура обрабатывает указанное событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>Части  
 `proceduredeclaration`  
 Объявление процедуры `Sub` для процедуры, которая будет обрабатывать событие.  
  
 `eventlist`  
 Список событий, обрабатываемых `proceduredeclaration`, с разделителями-запятыми. События должны вызываться базовым классом для текущего класса либо объектом, объявленным с помощью ключевого слова `WithEvents`.  
  
## <a name="remarks"></a>Примечания  
 Используйте ключевое слово `Handles` в конце объявления процедуры, чтобы она обрабатывала события, вызванные переменной объекта, которая объявлена с помощью ключевого слова `WithEvents` . Ключевое слово `Handles` может также использоваться в производном классе для обработки событий из базового класса.  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Дополнительные сведения см. в разделе [оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Для пользовательских событий приложение вызывает метод доступа `AddHandler` события во время добавления процедуры в качестве обработчика событий. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents&#2;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 В следующем примере показано, как производный класс может использовать оператор `Handles` для обработки события из базового класса.  
  
 [!code-vb[VbVbalrEvents&#3;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два обработчика событий кнопки для **приложение WPF** проекта.  
  
 [!code-vb[VbVbalrEvents&#41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример эквивалентен предыдущему примеру: `eventlist` в предложении `Handles` содержит события для обеих кнопок.  
  
 [!code-vb[VbVbalrEvents&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)

