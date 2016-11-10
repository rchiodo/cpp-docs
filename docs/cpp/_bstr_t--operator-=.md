---
title: "_bstr_t::operator ="
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator =, bstr"
  - "operator=, bstr"
  - "= operator, with specific Visual C++ objects"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
ms.author: "mblome"
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
# _bstr_t::operator =
**Microsoft Specific**  
  
 Assigns a new value to an existing `_bstr_t` object.  
  
## Syntax  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### Parameters  
 *s1*  
 A `_bstr_t` object to be assigned to an existing `_bstr_t` object.  
  
 *s2*  
 A multibyte string to be assigned to an existing `_bstr_t` object.  
  
 `s3`  
 A Unicode string to be assigned to an existing `_bstr_t` object.  
  
 `var`  
 A `_variant_t` object to be assigned to an existing `_bstr_t` object.  
  
 **END Microsoft Specific**  
  
## Example  
 See [_bstr_t::Assign](../cpp/_bstr_t--assign.md) for an example of using `operator=`.  
  
## See Also  
 [_bstr_t Class](../cpp/_bstr_t-class.md)