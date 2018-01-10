---
title: "CDBPropSet 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs: C++
helpviewer_keywords: CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b2523e37c3015bb49d123e99f39c1ea4bdb9045
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropset-class"></a>CDBPropSet 클래스
상속 되는 **DBPROPSET** 구조체를 추가 하는 키 필드를 초기화 하는 생성자와 `AddProperty` 메서드에 액세스 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|속성은 속성 집합을 추가 합니다.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|생성자입니다.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|설정의 **guidPropertySet** 필드는 **DBPROPSET** 구조입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 =](../../data/oledb/cdbpropset-operator-equal.md)|다른 설정 하는 하나의 속성의 콘텐츠를 할당 합니다.|  
  
## <a name="remarks"></a>설명  
 OLE DB 공급자와 소비자가 사용 하 여 **DBPROPSET** 의 배열을 전달 하는 구조 `DBPROP` 구조입니다. 각 `DBPROP` 구조 설정할 수 있는 단일 속성을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet 클래스](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET 구조](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP 구조](https://msdn.microsoft.com/en-us/library/ms717970.aspx)