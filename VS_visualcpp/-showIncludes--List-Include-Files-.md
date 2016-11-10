---
title: "-showIncludes (List Include Files)"
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
ms.topic: article
H1: /showIncludes (List Include Files)
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: 10
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
# -showIncludes (List Include Files)
Causes the compiler to output a list of the include files. Nested include files are also displayed (files that are included from the files that you include).  
  
## Syntax  
  
```  
/showIncludes  
```  
  
## Remarks  
 When an include file is encountered during compilation, a message is output, for example:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Nested include files are indicated by an indentation, one space for each level of nesting, for example:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 In this case, `2.h` was included from within `1.h`, hence the indentation.  
  
 The **/showIncludes** option emits to `stderr`, not `stdout`.  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [How to: Open Project Property Pages](../Topic/How%20to:%20Open%20Project%20Property%20Pages.md).  
  
2.  Click the **C/C++** folder.  
  
3.  Click the **Advanced** property page.  
  
4.  Modify the **Show Includes** property.  
  
### To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes?qualifyHint=False>.  
  
## See Also  
 [Compiler Options](../VS_visualcpp/Compiler-Options.md)   
 [Setting Compiler Options](../VS_visualcpp/Setting-Compiler-Options.md)