---
title: "Практическое руководство. Запись в текстовый файл (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c56095582561e4df19b164bc9a46b69a14da7c9d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Практическое руководство. Запись в текстовый файл (Руководство по программированию на C#)
В этих примерах показаны различные способы записи текста в файл.  В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=fullName> для записи каждого элемента любой IEnumerable\<строка> и строки в текстовый файл.  В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл.  В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.  
  
 Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.  Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C#.  
  
## <a name="example"></a>Пример  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 Во всех этих примерах осуществляется запись строковых литералов в файлы, но, вероятнее всего, вы будете использовать метод <xref:System.String.Format%2A>, который содержит множество параметров для записи различных типов значений, с выравниванием по левому или правому краю поля, с заполнением или без и т. д.  Вы также можете использовать функцию [интерполяции строк](../../../csharp/language-reference/keywords/interpolated-strings.md) C#.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Файл существует и является файлом только для чтения.  
  
-   Имя пути имеет слишком большую длину.  
  
-   Диск может быть переполнен.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)   
 [Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
