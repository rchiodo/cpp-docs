---
title: "WorkerArchetype::RequestType"
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
ms.topic: reference
ms.assetid: 22a4a478-9cbe-4230-b0b7-0f85ecb219dc
caps.latest.revision: 9
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
# WorkerArchetype::RequestType
A typedef for the type of work item that can be processed by the worker class.  
  
## Syntax  
  
```  
  
typedef   
MyRequestType  
 RequestType;  
  
```  
  
## Remarks  
 This type must be used as the first parameter of [Execute](../VS_visualcpp/WorkerArchetype--Execute.md) and must be capable of being cast to and from a ULONG_PTR.  
  
## Requirements  
 **Header:** atlutil.h  
  
## See Also  
 [Worker Archetype](../VS_visualcpp/Worker-Archetype.md)