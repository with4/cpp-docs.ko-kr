---
title: "ISessionPropertiesImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ISessionPropertiesImpl
dev_langs: C++
helpviewer_keywords: ISessionPropertiesImpl class
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ff8eda4d593ff0c6064313a7be243ec498b15c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl 클래스
구현을 제공는 [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `ISessionPropertiesImpl`합니다.  
  
 `PropClass`  
 기본값이 사용자 정의 가능한 속성 클래스 `T`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|현재 세션에 설정 된 세션 속성 그룹의 속성 목록을 반환 합니다.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|세션 속성 그룹의 속성을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 세션에 대해 필수 인터페이스입니다. 이 클래스가 정의 된 정적 함수를 호출 하 여 세션 속성을 구현 하는 [속성 집합 맵](../../data/oledb/begin-propset-map.md)합니다. 세션 클래스의 속성 집합 지도 지정 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)