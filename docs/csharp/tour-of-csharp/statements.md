---
title: "Операторы в C# | Краткий обзор языка C#"
description: "Все действия в программе C# определяются с помощью операторов"
keywords: ".NET, c#, операторы, синтаксис"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b5849264844a28ba02fb1f539de06b207be9cd26
ms.lasthandoff: 03/13/2017

---

# <a name="statements"></a>Операторы

Действия программы выражаются с помощью *операторов*. C# поддерживает несколько типов операторов, некоторые из которых определяются как внедренные операторы.

С помощью *блоков* можно использовать несколько операторов в таких контекстах, где ожидается только один оператор. Блок состоит из списка инструкций, заключенных между разделителями `{` и `}`.

*Операторы объявления* используются для объявления локальных переменных и констант.

*Операторы выражений* позволяют вычислять выражения. В качестве оператора можно использовать такие выражения, как вызовы методов, выделение объектов с помощью оператора `new`, назначения с помощью `=` и составных операторов присваивания, операторы `++` и `--` для приращения и уменьшения, а также выражения `await`.

*Операторы выбора* используются для выбора одного оператора из нескольких возможных вариантов в зависимости от значения какого-либо выражения. К этой группе относятся операторы `if` и `switch`.

*Операторы итерации* используются для многократного выполнения внедренного оператора. К этой группе относятся операторы `while`, `do`, `for` и `foreach`.

*Операторы перехода* используются для передачи управления. К этой группе относятся операторы `break`, `continue`, `goto`, `throw`, `return` и `yield`.

Операторы `try`...`catch` позволяют перехватывать исключения, создаваемые при выполнении блока кода, а оператор `try`...`finally` используется для указания кода завершения, который выполняется всегда, независимо от появления исключений.

Операторы `checked` и `unchecked` операторы позволяют управлять контекстом проверки переполнения для целочисленных арифметических операций и преобразований.

Оператор `lock` позволяет создать взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снять блокировку.

Оператор `using` используется для получения ресурса перед определенным оператором, и для удаления ресурса после его завершения.

Ниже перечислены виды операторов, которые вы можете использовать, и представлены примеры для каждого из них.

* Объявление локальной переменной.

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* Объявление локальной константы.

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* Оператор выражения.

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* Оператор `if`.

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* Оператор `switch`.

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* Оператор `while`.

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* Оператор `do`.

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* Оператор `for`.

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* Оператор `foreach`.

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* Оператор `break`.

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* Оператор `continue`.

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* Оператор `goto`.

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* Оператор `return`.

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* Оператор `yield`.

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* Операторы `throw` и операторы `try`.

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* Операторы `checked` и `unchecked`.

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* Оператор `lock`.

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* Оператор `using`.

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
[Назад](expressions.md)
[Вперед](classes-and-objects.md)

