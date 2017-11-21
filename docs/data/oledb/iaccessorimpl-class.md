---
title: "IAccessorImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IAccessorImpl
dev_langs: C++
helpviewer_keywords: IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9601c60f9942719a5360b30acb0c98d86b9300df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl 클래스
구현을 제공는 [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 행 집합이 나 명령 개체 클래스입니다.  
  
 `BindType`  
 바인딩 정보에 대 한 저장소 단위입니다. 기본값은는 **ATLBINDINGS** 구조 (atldb.h 참조).  
  
 `BindingVector`  
 열 정보에 대 한 저장소 단위입니다. 기본값은 [CAtlMap](../../atl/reference/catlmap-class.md) 여기서는 핵심 요소는 **HACCESSOR** 값과 value 요소에 대 한 포인터는는 `BindType` 구조입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|생성자입니다.|  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|기존 접근자에 대 한 참조 횟수를 추가합니다.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|바인딩 집합에서 접근자를 만듭니다.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|접근자 바인딩을 반환합니다.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|접근자를 해제 합니다.|  
  
## <a name="remarks"></a>설명  
 이 행 집합 및 명령에 필수입니다. OLE DB 공급자를 구현할 필요는 **HACCESSOR**, 하는 배열에 태그 [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 구조입니다. **HACCESSOR**제공한 s `IAccessorImpl` 의 주소는 `BindType` 구조입니다. 기본적으로 `BindType` 로 정의 된 **ATLBINDINGS** 에 `IAccessorImpl`의 템플릿 정의 합니다. `BindType`사용 하는 메커니즘을 제공 `IAccessorImpl` 에 있는 요소의 수를 추적 하는 **DBBINDING** 참조 개수 및 접근자 플래그 뿐만 아니라 배열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)