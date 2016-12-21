---
title: "IColumnsInfoImpl 클래스 | Microsoft Docs"
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
  - "ATL.IColumnsInfoImpl<T>"
  - "ATL::IColumnsInfoImpl"
  - "IColumnsInfoImpl"
  - "ATL.IColumnsInfoImpl"
  - "ATL::IColumnsInfoImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IColumnsInfoImpl 클래스"
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IColumnsInfoImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) interface.  
  
## 구문  
  
```  
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `IColumnsInfoImpl`.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|대부분의 소비자에 필요한 열 메타데이터를 반환합니다.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|지정된 열 ID로 식별되는 행 집합에 있는 열의 서수의 배열을 반환합니다.|  
  
## 설명  
 A mandatory interface on rowsets and commands.  To modify the behavior of your provider's `IColumnsInfo` implementation, you need to modify the provider column map.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)