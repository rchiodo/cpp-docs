---
title: "Compiler Error CS0708"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0708"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0708"
ms.assetid: 19e1907f-b78c-4c8b-b78c-eedfd57115f2
caps.latest.revision: 6
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Compiler Error CS0708
'field': cannot declare instance members in a static class  
  
 This error occurs if you declare a non-static member in a class that is declared static. It is not possible to create instances of static classes, so instance variables would not be meaningful. The **static** keyword should be applied to all members of static classes.  
  
 The following sample generates CS0708:  
  
```  
// CS0708.cs  
// compile with: /target:library  
public static class C  
{  
   int i;  // CS0708  
   static int j;  // OK  
}  
```