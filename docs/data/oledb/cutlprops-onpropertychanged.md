---
title: "CUtlProps::OnPropertyChanged | Microsoft Docs"
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
  - "OnPropertyChanged"
  - "CUtlProps.OnPropertyChanged"
  - "CUtlProps::OnPropertyChanged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnPropertyChanged 메서드"
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::OnPropertyChanged
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Called after setting a property to handle chained properties.  
  
## 구문  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### 매개 변수  
 `iCurSet`  
 The index into the property\-set array; zero if there is only one property set.  
  
 `pDBProp`  
 The property ID and new value in a [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) structure.  
  
## 반환 값  
 A standard `HRESULT`.  The default return value is `S_OK`.  
  
## 설명  
 If you want to handle chained properties, such as bookmarks or updates whose values are dependent on another property's value, you should override this function.  
  
## 예제  
 In this function, the user gets the property ID from the `DBPROP*` parameter.  Now, it is possible to compare the ID against a property to chain.  When the property is found, `SetProperties` is called with the property that will now be set in conjunction with the other property.  In this case, if one gets the `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, or `DBPROP_ORDEREDBOOKMARKS` property, one can set the `DBPROP_BOOKMARKS` property.  
  
 [!CODE [NVC_OLEDB_Provider#2](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#2)]  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)