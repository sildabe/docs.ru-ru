---
title: "Обзор универсальных типов (универсальных шаблонов)"
description: "Обзор универсальных типов (универсальных шаблонов)"
keywords: .NET, .NET Core
author: kuhlenh
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
translationtype: Human Translation
ms.sourcegitcommit: 5b1a76c011b95db3ff5c4b4e01556f79c45fb369
ms.openlocfilehash: 5dcb9d10aeded8c5e8956c4b99ba9675311a787a

---

# <a name="generic-types-generics-overview"></a>Обзор универсальных типов (универсальных шаблонов)

В C# мы постоянно используем универсальные шаблоны — как явно, так и неявно. Замечали ли вы, что работаете с IEnumerable<T> при использовании LINQ в C#? Или, может быть, вы замечали, что большинство методов возвращает IQueryable<T> в примере "универсального репозитория" для обращения к базам данных через Entity Framework? Возможно, вы задавались вопросом, что такое **T** в этих примерах и зачем это нужно?

Универсальные шаблоны, впервые появившиеся в .NET Framework 2.0, вносили изменения как для языка C#, так и для среды CLR. **Универсальные шаблоны** представляют собой "шаблон кода", позволяющий разработчикам определять [типобезопасные](https://msdn.microsoft.com/library/hbzz1a9a.aspx) структуры данных, не выполняя реальный тип данных. Например, `List<T>` — это [универсальная коллекция](https://msdn.microsoft.com/library/System.Collections.Generic.aspx), которую можно объявить и использовать с любым типом: `List<int>`, `List<string>`, `List<Person>` и т. д.

Так в чем же дело? Почему универсальные шаблоны так удобны? Чтобы понять это, нужно взглянуть на конкретный класс до и после добавления универсальных шаблонов. Давайте рассмотрим `ArrayList`. В C# 1.0 элементы `ArrayList` имели тип `object`. Это означало, что любой добавляемый элемент автоматически преобразовывался в `object`. То же самое происходит при чтении элементов из списка (этот процесс называется, соответственно, [упаковкой-](https://msdn.microsoft.com/library/yz2be5wk.aspx) и распаковкой-преобразованием). Упаковка-преобразование и распаковка-преобразование снижают производительность. Кроме того, во время компиляции невозможно определить, какой именно тип имеют данные в списке. Это приводит к созданию кода, который неудобно обслуживать. Универсальные шаблоны решают эту проблему, предоставляя дополнительные сведения о типе данных, которые будет содержать каждый экземпляр в списке. Проще говоря, вы можете добавить только целые числа в `List<int>`, только людей в `List<Person>` и т. д.

Универсальные шаблоны также доступны во время выполнения или **материализованы**. Это означает, что среда выполнения знает, какой тип структуры данных используется, и может хранить ее в памяти более эффективно.

Здесь приведена небольшая программа, иллюстрирующая пользу от сведений о типе структуры данных во время выполнения:

```cs
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }

```

Программа выдает следующие результаты:

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms

```

Прежде всего, здесь видно, что сортировка этого универсального списка осуществляется значительно быстрее, чем неуниверсального. Можно также заметить, что для универсального списка тип является конкретным ([System.Int32]), тогда как для неуниверсального списка — обобщенным. Поскольку среда выполнения знает, что универсальный `List<int>` имеет тип int, она может сохранить элементы списка в базовом целочисленном массиве в памяти, в то время как неуниверсальному `ArrayList` приходится приводить все элементы списка в качестве объекта, сохраненного в массиве объектов в памяти. Как показано в этом примере, лишние приведения занимают время и замедляют сортировку списка.

Последнее преимущество заключается в упрощении отладки. При отладке универсального шаблона в C# вы знаете тип каждого элемента в структуре данных. Без универсальных шаблонов вы бы не имели об этом никакого понятия.

## <a name="further-reading-and-resources"></a>Дополнительные сведения и ресурсы

*   [Введение в универсальные шаблоны C#](https://msdn.microsoft.com/library/ms379564.aspx)
*   [Руководство по программированию на C# — универсальные шаблоны](https://msdn.microsoft.com/library/512aeb7t.aspx)



<!--HONumber=Nov16_HO1-->

