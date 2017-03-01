---
title: "CAutoVectorPtr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoVectorPtr
- ATL.CAutoVectorPtr
- ATL.CAutoVectorPtr<T>
- CAutoVectorPtr
- ATL::CAutoVectorPtr<T>
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: bb4bbd110552d1e3cf604add44de7e428d2703ee
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr 클래스
이 클래스는 새 벡터를 사용 하 여 스마트 포인터 개체를 나타내는 및 delete 연산자입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CAutoVectorPtr
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 포인터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|생성자입니다.|  
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](#allocate)|가 가리키는 개체의 배열에 필요한 메모리를 할당 하려면이 메서드를 호출 `CAutoVectorPtr`합니다.|  
|[CAutoVectorPtr::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|  
|[CAutoVectorPtr::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|  
|[CAutoVectorPtr::Free](#free)|가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoVectorPtr`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|캐스트 연산자입니다.|  
|[CAutoVectorPtr::operator =](#operator_eq)|대입 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스를 만들고 범위에서 벗어나면 자동으로 리소스를 해제 하 여 메모리 누수를 방지 하는 데 도움이 되는 스마트 포인터를 관리 하기 위한 메서드를 제공 합니다. `CAutoVectorPtr`비슷합니다 `CAutoPtr`, 유일한 차이점은는 `CAutoVectorPtr` 사용 하 여 [벡터 new](../../standard-library/new-operators.md#operator_new_arr) 및 [벡터 delete](../../standard-library/new-operators.md#operator_delete_arr) c + +는 대신 메모리 할당과 해제를 **새** 및 **삭제** 연산자입니다. 참조 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 경우 컬렉션 클래스의 `CAutoVectorPtr` 필요 합니다.  

  
 참조 [CAutoPtr](../../atl/reference/cautoptr-class.md) 스마트 포인터 클래스를 사용 하 여의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-nameallocatea--cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr::Allocate  
 가 가리키는 개체의 배열에 필요한 메모리를 할당 하려면이 메서드를 호출 `CAutoVectorPtr`합니다.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nElements`  
 배열의 요소 수입니다.  
  
### <a name="return-value"></a>반환 값  
 True를 반환 하는 메모리는 성공적으로 할당 실패 한 경우 false.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 어설션 오류는 경우에 [CAutoVectorPtr::m_p](#m_p) 멤버 변수는 현재 기존 값을 가리킵니다; 즉,가 아닌 NULL로 합니다.  
  
##  <a name="a-nameattacha--cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr::Attach  
 이 메서드는 기존 포인터의 소유권을 호출 합니다.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 `CAutoVectorPtr` 개체는이 포인터의 소유권을 갖게 됩니다.  
  
### <a name="remarks"></a>주의  
 때는 `CAutoVectorPtr` 자동으로 삭제 하는 포인터 할당 된 모든 데이터 범위를 벗어나면, 개체 포인터의 소유권을 갖습니다. 경우 [CAutoVectorPtr::Detach](#detach) 은 호출 프로그래머가 다시 모든 해제에 대 한 책임 지정 된 리소스가 할당 됩니다.  
  
 디버그 빌드에서 어설션 오류는 경우에 [CAutoVectorPtr::m_p](#m_p) 멤버 변수는 현재 기존 값을 가리킵니다; 즉,가 아닌 NULL로 합니다.  
  
##  <a name="a-namecautovectorptra--cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr  
 생성자입니다.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 기존 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `CAutoVectorPtr` 는 기존 포인터를 사용 하 여 개체를 만들 수 있습니다,이 경우에 포인터 소유권 전송 합니다.  
  
##  <a name="a-namedtora--cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr  
 소멸자입니다.  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다. 호출 [CAutoVectorPtr::Free](#free)합니다.  
  
##  <a name="a-namedetacha--cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::Detach  
 포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 포인터의 복사본을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 포인터의 소유권을 해제, 설정 된 [CAutoVectorPtr::m_p](#m_p) 멤버 변수를 NULL, 포인터의 복사본을 반환 합니다. 호출한 후 **분리**를 해제 하 여 프로그래머의 몫 리소스가 할당 됩니다 매길는 `CAutoVectorPtr` 개체 수 이전에 독자를 대상으로 해야 합니다.  
  
##  <a name="a-namefreea--cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr::Free  
 가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoVectorPtr`합니다.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>주의  
 가 가리키는 개체는 `CAutoVectorPtr` 해제 되 면 및 [CAutoVectorPtr::m_p](#m_p) 멤버 변수는 NULL로 설정 됩니다.  
  
##  <a name="a-namempa--cautovectorptrmp"></a><a name="m_p"></a>CAutoVectorPtr::m_p  
 포인터 데이터 멤버 변수입니다.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수는 포인터 정보를 보유합니다.  
  
##  <a name="a-nameoperatoreqa--cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr::operator =  
 대입 연산자입니다.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조를 반환 합니다.는 **CAutoVectorPtr\< T >**합니다.  
  
### <a name="remarks"></a>주의  
 대입 연산자를 분리는 `CAutoVectorPtr` 개체에서 모든 현재 포인터 새 포인터를 연결 하 고 `p`, 그 자리에 있습니다.  
  
##  <a name="a-nameoperatortstara--cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 캐스트 연산자입니다.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>주의  
 클래스 템플릿에 정의 된 개체 데이터 형식에 대 한 포인터를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAutoPtr 클래스](../../atl/reference/cautoptr-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

