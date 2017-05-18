---
title: "IAtlStringMgr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4ff4aa01a6d30f377560962f98a5892bdcc37837
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr 클래스
이 클래스는 인터페이스를 나타냅니다.는 `CStringT` 메모리 관리자입니다.  
  
## <a name="syntax"></a>구문  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[할당](#allocate)|새 문자열 데이터 구조를 할당 하려면이 메서드를 호출 합니다.|  
|[복제](#clone)|다른 인스턴스와 함께 사용 하기 위해 새 문자열 관리자에 대 한 포인터를 반환 하려면이 메서드를 호출 `CSimpleStringT`합니다.|  
|[무료](#free)|이 메서드는 문자열 데이터 구조를 호출 합니다.|  
|[GetNilString](#getnilstring)|에 대 한 포인터를 반환 합니다.는 `CStringData` 빈 문자열 개체에서 사용 되는 개체입니다.|  
|[다시 할당](#reallocate)|문자열 데이터 구조를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 MFC에 독립적인 문자열 클래스;에 사용 되는 메모리 관리 와 같은 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), 및 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)합니다.  
  
 또한 사용자 지정 문자열 클래스에 대 한 사용자 지정 메모리 관리자를 구현 하려면이 클래스를 사용할 수 있습니다. 자세한 내용은 참조 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpstr.h  
  
##  <a name="allocate"></a>IAtlStringMgr::Allocate  
 새 문자열 데이터 구조를 할당합니다.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nAllocLength`  
 새 메모리 블록에 있는 문자의 수입니다.  
  
 `nCharSize`  
 크기 (바이트) 문자열 관리자에서 사용 하는 문자 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 할당된 메모리 블록에 대한 포인터를 반환합니다.  
  
> [!NOTE]
>  예외를 throw 하 여 실패 한 할당을 신호 마십시오. 대신, 실패 한 할당 해야 신호를 보낼 수를 반환 하 여 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 호출 [IAtlStringMgr::Free](#free) 또는 [IAtlStringMgr::ReAllocate](#reallocate) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
> [!NOTE]
>  사용 예제를 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
##  <a name="clone"></a>IAtlStringMgr::Clone  
 다른 인스턴스와 함께 사용 하기 위해 새 문자열 관리자에 대 한 포인터를 반환 `CSimpleStringT`합니다.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>반환 값  
 복사본을 반환 된 `IAtlStringMgr` 개체입니다.  
  
### <a name="remarks"></a>주의  
 문자열 관리자는 새 문자열에 필요할 때 일반적으로 프레임 워크에서 호출 합니다. 대부분의 경우에는 **이** 포인터가 반환 됩니다.  
  
 그러나 메모리 관리자의 여러 인스턴스에서 사용 되 고 지원 하지 않는 경우 `CSimpleStringT`를 공유할 수 있는 문자열 관리자에 대 한 포인터를 반환 합니다.  
  
> [!NOTE]
>  사용 예제를 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
##  <a name="free"></a>IAtlStringMgr::Free  
 문자열 데이터 구조를 해제합니다.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 해제할 메모리 블록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이전에 할당 하 여 지정 된 메모리 블록을 해제 [Allocate](#allocate) 또는 [재할당](../../atl/reference/iatlmemmgr-class.md#reallocate)합니다.  
  
> [!NOTE]
>  사용 예제를 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
##  <a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 빈 문자열에 대 한 문자열 데이터 구조에 대 한 포인터를 반환합니다.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CStringData` 을 빈 문자열을 나타내는 개체입니다.  
  
### <a name="remarks"></a>주의  
 빈 문자열 표현을 반환 하려면이 함수를 호출 합니다.  
  
> [!NOTE]
>  사용자 지정 문자열 관리자를 구현할 때는이 함수는 실패 하지 해야 합니다. 인스턴스를 포함 하 여이 확인할 수 있습니다 **CNilStringData** 문자열 manager 클래스 및 해당 인스턴스에 대 한 포인터를 반환 합니다.  
  
> [!NOTE]
>  사용 예제를 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
##  <a name="reallocate"></a>IAtlStringMgr::Reallocate  
 문자열 데이터 구조를 다시 할당합니다.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 이 메모리 관리자가 이전에 할당 된 메모리 포인터입니다.  
  
 `nAllocLength`  
 새 메모리 블록에 있는 문자의 수입니다.  
  
 `nCharSize`  
 크기 (바이트) 문자열 관리자에서 사용 하는 문자 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.  
  
### <a name="remarks"></a>주의  
 으로 지정 된 기존 메모리 블록의 크기를 조정 하려면이 함수를 호출 `pData`합니다.  
  
 호출 [IAtlStringMgr::Free](#free) 이 메서드에서 할당 된 메모리를 해제 합니다.  
  
> [!NOTE]
>  사용 예제를 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)



