---
title: "Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d20d75b2492c214305c07a5e19941cd91b66f67
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции
В этом примере показано, как выполняется добавление, получение, обновление и удаление элементов из класса <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>. Этот класс коллекций является потокобезопасной реализацией. Рекомендуется использовать его каждый раз, когда множество потоков одновременно могут пытаться получить доступ к элементам.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> предоставляет несколько удобных методов, которые позволяют обойтись без первоначальной проверки существования ключа перед добавлением или удалением данных. В таблице ниже перечислены эти удобные методы и приводится описание их использования.  
  
|Метод|Используется, если…|  
|------------|---------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Необходимо добавить новое значение для заданного ключа, а также в том случае, если ключ уже существует и необходимо заменить его значение.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Необходимо получить существующее значение для заданного ключа, а также в том случае, если ключ не существует, и задать значение паре "ключ-значение".|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Необходимо добавить, получить, обновить или удалить пару "ключ-значение", а также в том случае, если ключ уже существует или попытка завершилась по какой-либо причине ошибкой и необходимо выполнить альтернативные действия.|  
  
## <a name="example"></a>Пример  
 В следующем примере используются два экземпляра <xref:System.Threading.Tasks.Task> для одновременного добавления некоторых элементов в <xref:System.Collections.Concurrent.ConcurrentDictionary%602> и последующего вывода всего содержимого, чтобы показать, что элементы успешно добавлены. В примере также показано использование методов <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> для добавления, обновления и получения элементов из коллекции.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> предназначен для многопоточных сценариев. Необязательно использовать блокировки в коде для добавления или удаления элементов из коллекции. Однако всегда есть возможность для одного потока получить значение, а для другого потока немедленно обновить коллекцию, передавая тому же ключу новое значение.  
  
 Кроме того, несмотря на то, что все методы <xref:System.Collections.Concurrent.ConcurrentDictionary%602> являются потокобезопасными, не все методы являются атомарными, в частности <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Пользовательский делегат, передаваемый этим методам, вызывается вне внутренней блокировки словаря. (Это позволяет предотвратить блокировку всех потоков неизвестным кодом.) Поэтому может произойти следующая последовательность событий.  
  
 1\) Поток threadA вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, не находит элемент и создает новый элемент для добавления (Add), вызывая делегат valueFactory.  
  
 2\) Поток threadB одновременно вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, делегат valueFactory вызван, этот поток оказывается во внутренней блокировке раньше потока threadA, его новая пара "ключ — значение" добавляется в словарь.  
  
 3\) Пользовательский делегат потока threadA завершает работу, поток достигает блокировки, но видит, что теперь элемент уже существует.  
  
 4\) Поток threadA выполняет действие Get и возвращает данные, добавленные ранее потоком threadB.  
  
 Поэтому нет гарантии, что данные, возвращаемые методом <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, будут данными, созданными делегатом valueFactory потока. Аналогичная последовательность событий может произойти при вызове метода <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
