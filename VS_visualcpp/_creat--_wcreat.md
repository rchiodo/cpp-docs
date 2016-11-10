---
title: "_creat, _wcreat"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - _creat
  - _wcreat
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
  - api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 19
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# _creat, _wcreat
Creates a new file. `_creat` and `_wcreat` have been deprecated; use [_sopen_s, _wsopen_s](../VS_visualcpp/_sopen_s--_wsopen_s.md) instead.  
  
## Syntax  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### Parameters  
 `filename`  
 Name of new file.  
  
 `pmode`  
 Permission setting.  
  
## Return Value  
 These functions, if successful, return a file descriptor to the created file. Otherwise, the functions return –1 and set `errno` as shown in the following table.  
  
|`errno` setting|Description|  
|---------------------|-----------------|  
|`EACCES`|`filename` specifies an existing read-only file or specifies a directory instead of a file.|  
|`EMFILE`|No more file descriptors are available.|  
|`ENOENT`|Specified file could not be found.|  
  
 If `filename` is NULL, these functions invoke the invalid parameter handler, as described in [Parameter Validation](../VS_visualcpp/Parameter-Validation.md). If execution is allowed to continue, these functions set `errno` to `EINVAL` and return -1.  
  
 For more information about these and other return codes, see [_doserrno, errno, _sys_errlist, and _sys_nerr](../VS_visualcpp/errno--_doserrno--_sys_errlist--and-_sys_nerr.md).  
  
## Remarks  
 The `_creat` function creates a new file or opens and truncates an existing one. `_wcreat` is a wide-character version of `_creat`; the `filename` argument to `_wcreat` is a wide-character string. `_wcreat` and `_creat` behave identically otherwise.  
  
### Generic-Text Routine Mappings  
  
|Tchar.h routine|_UNICODE and _MBCS not defined|_MBCS defined|_UNICODE defined|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 If the file specified by `filename` does not exist, a new file is created with the given permission setting and is opened for writing. If the file already exists and its permission setting allows writing, `_creat` truncates the file to length 0, destroying the previous contents, and opens it for writing. The permission setting, `pmode`, applies to newly created files only. The new file receives the specified permission setting after it is closed for the first time. The integer expression `pmode` contains one or both of the manifest constants `_S_IWRITE` and `_S_IREAD`, defined in SYS\Stat.h. When both constants are given, they are joined with the bitwise `OR` operator ( **&#124;** ). The `pmode` parameter is set to one of the following values.  
  
|Value|Definition|  
|-----------|----------------|  
|`_S_IWRITE`|Writing permitted.|  
|`_S_IREAD`|Reading permitted.|  
|`_S_IREAD &#124; _S_IWRITE`|Reading and writing permitted.|  
  
 If write permission is not given, the file is read-only. All files are always readable; it is impossible to give write-only permission. The modes `_S_IWRITE` and `_S_IREAD``| _S_IWRITE` are then equivalent. Files opened using `_creat` are always opened in compatibility mode (see [_sopen](../VS_visualcpp/_sopen--_wsopen.md)) with `_SH_DENYNO`.  
  
 `_creat` applies the current file-permission mask to `pmode` before setting the permissions (see [_umask](../VS_visualcpp/_umask.md)). `_creat` is provided primarily for compatibility with previous libraries. A call to `_open` with `_O_CREAT` and `_O_TRUNC` in the `oflag` parameter is equivalent to `_creat` and is preferable for new code.  
  
## Requirements  
  
|Routine|Required header|Optional header|  
|-------------|---------------------|---------------------|  
|`_creat`|<io.h>|<sys/types.h>, <sys/stat.h>, <errno.h>|  
|`_wcreat`|<io.h> or <wchar.h>|<sys/types.h>, <sys/stat.h>, <errno.h>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## Example  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
 **Created data file.**   
## See Also  
 [Low-Level I/O](../VS_visualcpp/Low-Level-I-O.md)   
 [_chmod, _wchmod](../VS_visualcpp/_chmod--_wchmod.md)   
 [_chsize](../VS_visualcpp/_chsize.md)   
 [_close](../VS_visualcpp/_close.md)   
 [_dup, _dup2](../VS_visualcpp/_dup--_dup2.md)   
 [_open, _wopen](../VS_visualcpp/_open--_wopen.md)   
 [_sopen, _wsopen](../VS_visualcpp/_sopen--_wsopen.md)   
 [_umask](../VS_visualcpp/_umask.md)