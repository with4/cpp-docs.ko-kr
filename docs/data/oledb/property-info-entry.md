---
title: "PROPERTY_INFO_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY 매크로"
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성 집합의 특정 속성을 나타냅니다.  
  
## 구문  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### 매개 변수  
 *dwPropID*  
 \[in\] 속성 집합 GUID와 함께 사용하여 속성을 식별할 수 있는 [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 값입니다.  
  
## 설명  
 이 매크로는 `DWORD` 형식의 속성 값을 ATLDB.H에 정의된 기본값으로 설정합니다. 속성을 선택한 값으로 설정하려면 [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md)를 사용합니다. 속성에 대한 [VARTYPE](http://msdn.microsoft.com/ko-kr/317b911b-1805-402d-a9cb-159546bc88b4) 및 [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx)를 동시에 설정하려면 [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)를 사용합니다.  
  
## 예제  
 [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md)을 참조하세요.  
  
## 요구 사항  
 **헤더:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)