---
title: "Data Source: Programmatically Creating a Table in an ODBC Data Source"
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
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
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
# Data Source: Programmatically Creating a Table in an ODBC Data Source
This topic explains how to create a table for your data source, using the `ExecuteSQL` member function of class `CDatabase`, passing the function a string that contains a **CREATE TABLE** SQL statement.  
  
 For general information about ODBC data sources in MFC, see [Data Source (ODBC)](../VS_visualcpp/Data-Source--ODBC-.md). The topic [Data Source: Programmatically Configuring an ODBC Data Source](../VS_visualcpp/Data-Source--Programmatically-Configuring-an-ODBC-Data-Source.md) describes creating data sources.  
  
 When you have the data source established, you can easily create tables using the `ExecuteSQL` member function and the **CREATE TABLE** SQL statement. For example, if you had a `CDatabase` object called `myDB`, you could use the following MFC code to create a table:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 This code example creates a table called "OFFICES" in the Microsoft Access data source connection maintained by `myDB`; the table contains two fields "OfficeID" and "OfficeName."  
  
> [!NOTE]
>  The field types specified in the **CREATE TABLE** SQL statement might vary according to the ODBC driver that you are using. The Microsoft Query program (distributed with Visual C++ 1.5) is one way to discover what field types are available for a data source. In Microsoft Query, click **File**, click **Table_Definition**, select a table from a data source, and look at the type shown in the **Type** combo box. SQL syntax also exists to create indexes.  
  
## See Also  
 [Data Source (ODBC)](../VS_visualcpp/Data-Source--ODBC-.md)