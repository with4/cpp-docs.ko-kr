---
title: "동적 접근자 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "접근자[C++], 동적"
  - "동적 접근자"
  - "재정의, 동적 접근자"
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 동적 접근자 재정의
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDynamicAccessor` 같은 동적 접근자를 사용할 때, 명령 **Open** 메서드는 열린 행 집합의 열 정보를 기반으로 하여 사용자에 대한 접근자를 자동으로 만듭니다.  동적 접근자를 재정의하면 열이 바인딩되는 방법을 정확하게 제어할 수 있습니다.  
  
 동적 접근자를 재정의하려면 **false**를 마지막 매개 변수로서 `CCommand::Open` 메서드에 전달합니다.  이렇게 하면 **Open**은 접근자를 자동으로 만들 수 없습니다.  그런 다음 `GetColumnInfo`를 호출한 후 바인딩할 각 열에 대해 `AddBindEntry`를 호출합니다.  다음 코드는 이 작업을 수행하는 방법에 대해 보여 줍니다.  
  
```  
USES_CONVERSION;  
double   dblProductID;  
  
CCommand<CDynamicAccessor> product;  
// Open the table, passing false to prevent automatic binding   
product.Open(session, _T("Select * FROM Products"), NULL, NULL, DBGUID_DEFAULT, false);  
  
ULONG         nColumns;  
DBCOLUMNINFO*   pColumnInfo;  
// Get the column information from the opened rowset.  
product.GetColumnInfo(&nColumns, &pColumnInfo);  
  
// Bind the product ID as a double.  
pColumnInfo[0].wType          = DBTYPE_R8;  
pColumnInfo[0].ulColumnSize = 8;  
product.AddBindEntry(pColumnInfo[0]);  
  
// Bind the product name as it is.  
product.AddBindEntry(pColumnInfo[1]);  
  
// Bind the reorder level as a string.  
pColumnInfo[8].wType          = DBTYPE_STR;  
pColumnInfo[8].ulColumnSize = 10;  
product.AddBindEntry(pColumnInfo[8]);  
  
// You have finished specifying the bindings. Go ahead and bind.  
product.Bind();  
// Free the memory for the column information that was retrieved in   
// previous call to GetColumnInfo.  
CoTaskMemFree(pColumnInfo);  
  
char*   pszProductName;  
char*   pszReorderLevel;  
bool   bRC;  
  
// Loop through the records tracing out the information.  
while (product.MoveNext() == S_OK)  
{  
   bRC = product.GetValue(1, &dblProductID);  
   pszProductName   = (char*)product.GetValue(2);  
   pszReorderLevel  = (char*)product.GetValue(9);  
  
   ATLTRACE(_T("Override = %lf \"%s\" \"%s\"\n"), dblProductID,  
      A2T(pszProductName), A2T(pszReorderLevel));  
}  
```  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)