---
title: "IDBSchemaRowsetImpl::GetSchemas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBSchemaRowsetImpl::GetSchemas"
  - "GetSchemas"
  - "IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "ATL.IDBSchemaRowsetImpl.GetSchemas"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "IDBSchemaRowsetImpl.GetSchemas"
  - "IDBSchemaRowsetImpl::GetSchemas"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSchemas 메서드"
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::GetSchemas
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)에서 액세스할 수 있는 스키마 행 집합 목록을 반환합니다.  
  
## 구문  
  
```  
  
STDMETHOD  
( GetSchema s )(  
   ULONG *   
pcSchemas  
,  
   GUID **   
prgSchemas  
,  
   ULONG**   
prgRest  
);  
  
```  
  
#### 매개 변수  
 *pcSchemas*  
 \[out\] 스키마 수로 채워진 **ULONG**의 포인터입니다.  
  
 *prgSchemas*  
 \[out\] 스키마 행 집합 GUID 배열의 포인터로 채워진 GUID 배열의 포인터입니다.  
  
 *prgRest*  
 \[out\] 제한 배열로 채울 **ULONG** 배열의 포인터입니다.  
  
## 설명  
 이 메서드는 공급자가 지원하는 모든 스키마 행 집합의 배열을 반환합니다.[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]에서 [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx)를 참조하세요.  
  
 이 함수를 구현하려면 사용자에게 세션 클래스의 스키마 맵이 있어야 합니다. 스키마 맵 정보를 사용하는 경우 맵의 스키마에 대한 GUID 배열로 응답합니다. 이는 공급자가 지원하는 스키마를 나타냅니다.  
  
## 요구 사항  
 **헤더:** atldb.h  
  
## 참고 항목  
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ko-kr/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)