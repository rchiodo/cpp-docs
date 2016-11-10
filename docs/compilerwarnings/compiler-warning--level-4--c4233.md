---
title: "Compiler Warning (level 4) C4233"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Compiler Warning (level 4) C4233
nonstandard extension used : 'keyword' keyword only supported in C++, not C  
  
 The compiler compiled your source code as C rather than C++, and you used a keyword that is only valid in C++. The compiler compiles your source file as C if the extension of the source file is .c or you use [/Tc](../buildref/-tc---tp---tc---tp--specify-source-file-type-.md).  
  
 This warning is automatically promoted to an error. If you wish to modify this behavior, use [#pragma warning](../c/warning.md). For example, to make C4233 into a level 4 warning issue,  
  
```  
#pragma warning(2:4233)  
```  
  
 in your source code file.