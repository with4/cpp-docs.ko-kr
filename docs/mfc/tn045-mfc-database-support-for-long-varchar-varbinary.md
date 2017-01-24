---
title: "TN045: Long Varchar/Varbinary에 대한 MFC/데이터베이스 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN045"
  - "Varbinary 데이터 형식"
  - "Varchar 데이터 형식"
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN045: Long Varchar/Varbinary에 대한 MFC/데이터베이스 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 This note describes how to retrieve and send the ODBC **SQL\_LONGVARCHAR** and **SQL\_LONGVARBINARY** data types using the MFC database classes.  
  
## Overview of Long Varchar\/Varbinary Support  
 The ODBC **SQL\_LONG\_VARCHAR** and **SQL\_LONGBINARY** data types \(referred to here as long data columns\) can hold huge amounts of data.  There are 3 ways you can handle this data:  
  
-   Bind it to a `CString`\/`CByteArray`.  
  
-   Bind it to a `CLongBinary`.  
  
-   Do not bind it at all and retrieve and send the long data value manually, independent of the database classes.  
  
 Each of the three methods has advantages and disadvantages.  
  
 Long data columns are not supported for parameters to a query.  They are only supported for outputColumns.  
  
## Binding a Long Data Column to a CString\/CByteArray  
 장점  
  
 This approach is simple to understand, and you work with familiar classes.  The framework provides `CFormView` support for `CString` with `DDX_Text`.  You have lots of general string or collection functionality with the `CString` and `CByteArray` classes, and you can control the amount of memory allocated locally to hold the data value.  The framework maintains an old copy of field data during **Edit** or `AddNew` function calls, and the framework can automatically detect changes to the data for you.  
  
> [!NOTE]
>  Since `CString` is designed for working on character data, and `CByteArray` for working on binary data, it is recommended that you put the character data \(**SQL\_LONGVARCHAR**\) into `CString`, and the binary data \(**SQL\_LONGVARBINARY**\) into `CByteArray`.  
  
 The RFX functions for `CString` and `CByteArray` have an additional argument which lets you override the default size of allocated memory to hold the retrieved value for the data column.  Note the nMaxLength argument in the following function declarations:  
  
```  
void AFXAPI RFX_Text(CFieldExchange* pFX, const char *szName,  
    CString& value, int nMaxLength = 255, int nColumnType =  
    SQL_VARCHAR);  
  
void AFXAPI RFX_Binary(CFieldExchange* pFX, const char *szName,   
    CByteArray& value,int nMaxLength = 255);  
```  
  
 If you retrieve a long data column into a `CString` or `CByteArray`, the maximum returned amount of data is, by default, 255 bytes.  Anything beyond this is ignored.  In this case, the framework will throw the exception **AFX\_SQL\_ERROR\_DATA\_TRUNCATED**.  Fortunately, you can explicitly increase nMaxLength to greater values, up to **MAXINT**.  
  
> [!NOTE]
>  The value of nMaxLength is used by MFC to set the local buffer of the **SQLBindColumn** function.  This is the local buffer for storage of the data and does not actually affect the amount of data returned by the ODBC driver.  `RFX_Text` and `RFX_Binary` only make one call using **SQLFetch** to retrieve the data from the back\-end database.  Each ODBC driver has a different limitation on the amount of data they can return in a single fetch.  This limit may be much smaller than the value set in nMaxLength, in which case the exception **AFX\_SQL\_ERROR\_DATA\_TRUNCATED** will be thrown.  Under these circumstances, switch to using `RFX_LongBinary` instead of `RFX_Text` or `RFX_Binary` so that all the data can be retrieved.  
  
 ClassWizard will bind a **SQL\_LONGVARCHAR** to a `CString`, or a **SQL\_LONGVARBINARY** to a `CByteArray` for you.  If you want to allocate more than 255 bytes into which you retrieve your long data column, you can then supply an explicit value for nMaxLength.  
  
 When a long data column is bound to a `CString` or `CByteArray`, updating the field works just the same as when it is bound to a SQL\_**VARCHAR** or SQL\_**VARBINARY**.  During **Edit**, the data value is cached away and later compared when **Update** is called to detect changes to the data value and set the Dirty and Null values for the column appropriately.  
  
## Binding a Long Data Column to a CLongBinary  
 If your long data column may contain more **MAXINT** bytes of data, you should probably consider retrieving it into a `CLongBinary`.  
  
 장점  
  
 This retrieves an entire long data column, up to available memory.  
  
 단점  
  
 The data is held in memory.  This approach is also prohibitively expensive for very large amounts of data.  You must call `SetFieldDirty` for the bound data member to ensure the field is included in an **Update** operation.  
  
 If you retrieve long data columns into a `CLongBinary`, the database classes will check the total size of the long data column, then allocate an `HGLOBAL` memory segment large enough to hold it the entire data value.  The database classes then retrieve the entire data value into the allocated `HGLOBAL`.  
  
 If the data source cannot return the expected size of the long data column, the framework will throw the exception **AFX\_SQL\_ERROR\_SQL\_NO\_TOTAL**.  If the attempt to allocate the `HGLOBAL` fails, a standard memory exception is thrown.  
  
 ClassWizard will bind an **SQL\_LONGVARCHAR** or **SQL\_LONGVARBINARY** to a `CLongBinary` for you.  Select `CLongBinary` as the Variable Type in the Add Member Variable dialog.  ClassWizard will then add an `RFX_LongBinary` call to your `DoFieldExchange` call and increment the total number of bound fields.  
  
 To update long data column values, first make sure the allocated `HGLOBAL` is large enough to hold your new data by calling **::GlobalSize** on the `m_hData` member of the `CLongBinary`.  If it is too small, release the `HGLOBAL` and allocate one the appropriate size.  Then set `m_dwDataLength` to reflect the new size.  
  
 Otherwise, if `m_dwDataLength` is larger than the size of the data you're replacing, you can either free and reallocate the `HGLOBAL`, or leave it allocated.  Make sure to indicate the number of bytes actually used in `m_dwDataLength`.  
  
## How Updating a CLongBinary Works  
 It is not necessary to understand how updating a `CLongBinary` works, but it may be useful as an example on how to send long data values to a data source, if you choose this third method, described below.  
  
> [!NOTE]
>  In order for a `CLongBinary` field to be included in an update, you must explicitly call `SetFieldDirty` for the field.  If you make any change to a field, including setting it Null, you must call `SetFieldDirty`.  You must also call `SetFieldNull`, with the second parameter being **FALSE**, to mark the field as having a value.  
  
 When updating a `CLongBinary` field, the database classes use ODBC's **DATA\_AT\_EXEC** mechanism \(see ODBC documentation on **SQLSetPos**'s rgbValue argument\).  When the framework prepares the insert or update statement, instead of pointing to the `HGLOBAL` containing the data, the *address* of the `CLongBinary` is set as the *value* of the column instead, and the length indicator set to **SQL\_DATA\_AT\_EXEC**.  Later, when the update statement is sent to the data source, **SQLExecDirect** will return **SQL\_NEED\_DATA**.  This alerts the framework that the value of the param for this column is actually the address of a `CLongBinary`.  The framework calls **SQLGetData** once with a small buffer, expecting the driver to return the actual length of the data.  If the driver returns the actual length of the binary large object \(the BLOB\), MFC reallocates as much space as necessary to fetch the BLOB.  If the data source returns **SQL\_NO\_TOTAL**, indicating that it can't determine the size of the BLOB, MFC will create smaller blocks.  The default initial size is 64K, and subsequent blocks will be double the size; for example, the second will be 128K, the third is 256K, and so on.  The initial size is configurable.  
  
## Not Binding: Retrieving\/Sending Data Directly from ODBC with SQLGetData  
 With this method you completely bypass the database classes, and deal with the long data column yourself.  
  
 장점  
  
 You can cache data to disk if necessary, or decide dynamically how much data to retrieve.  
  
 단점  
  
 You don't get the framework's **Edit** or `AddNew` support, and you must write code yourself to perform basic functionality \(**Delete** does work though, since it is not a column level operation\).  
  
 In this case, the long data column must be in the select list of the recordset, but should not be bound to by the framework.  One way to do this is to supply your own SQL statement via `GetDefaultSQL` or as the lpszSQL argument to `CRecordset`'s **Open** function, and not bind the extra column with an RFX\_ function call.  ODBC requires that unbound fields appear to the right of bound fields, so add your unbound column or columns to the end of the select list.  
  
> [!NOTE]
>  Because your long data column is not bound by the framework, changes to it will not be handled with `CRecordset::Update` calls.  You must create and send the required SQL **INSERT** and **UPDATE** statements yourself.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)