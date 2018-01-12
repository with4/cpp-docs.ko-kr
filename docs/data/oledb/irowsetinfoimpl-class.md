---
title: "IRowsetInfoImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs: C++
helpviewer_keywords: IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cba03cfdda0b7a55c8f4719d5340566ee5dc6050
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl 클래스
에 대 한 구현을 제공는 [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IRowsetInfoImpl`합니다.  
  
 `PropClass`  
 기본값이 사용자 정의 가능한 속성 클래스 `T`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|행 집합에서 지 원하는 모든 속성의 현재 설정을 반환 합니다.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|이 행 집합을 만든 개체 (명령 또는 세션)에 대 한 인터페이스 포인터를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 행 집합에 필수 인터페이스입니다. 이 클래스를 사용 하 여 행 집합 속성을 구현 하는 [속성 매핑이 두 집합](../../data/oledb/begin-propset-map.md) 명령 클래스에 정의 합니다. 명령 클래스의 속성을 사용 하 여 수를 설정 하는 행 집합 클래스 보이지만 명령 또는 세션 개체에 의해 생성 될 때 행 집합 런타임 속성의 자체 복사본과 함께 제공 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** altdb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)