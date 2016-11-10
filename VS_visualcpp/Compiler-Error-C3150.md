---
title: "Compiler Error C3150"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: error-reference
ms.assetid: c1ff28f5-52fe-4fd4-81d0-2e0ad8548631
caps.latest.revision: 11
manager: ghogen
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
---
# Compiler Error C3150
'element' : 'attribute' can only be applied to a class, interface, array or pointer  
  
 [__gc](../Topic/__gc.md) can only be used on a class, interface, or array.  
  
 C3150 is only reachable using **/clr:oldSyntax**.  
  
 The following sample generates C3150:  
  
```  
// C3150.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc void f()   // C3150; function cannot be managed  
{  
}  
```