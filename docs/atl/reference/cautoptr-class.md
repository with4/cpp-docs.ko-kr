---
title: "CAutoPtr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
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
ms.openlocfilehash: 309a3d0ddceab2995c85e156c7db09ddd7edfa86
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptr-class"></a>CAutoPtr 클래스
이 클래스는 스마트 포인터 개체를 나타냅니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 포인터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|생성자입니다.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|  
|[CAutoPtr::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|  
|[CAutoPtr::Free](#free)|가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoPtr`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|캐스트 연산자입니다.|  
|[CAutoPtr::operator =](#operator_eq)|대입 연산자입니다.|  
|[-> CAutoPtr::operator](#operator_ptr)|멤버 포인터 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|포인터 데이터 멤버 변수입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스를 만들고 범위에서 벗어나면 자동으로 리소스를 해제 하 여 메모리 누수를 방지 하는 데 도움이 되는 스마트 포인터를 관리 하기 위한 메서드를 제공 합니다.  
  
 또한 `CAutoPtr`의 복사 생성자와 대입 연산자 소유권 포인터의 대상 포인터를 소스 파일에 대 한 포인터를 복사 하 고 NULL로 원본 포인터를 설정 합니다. 따라서 두 개의 수 없는 `CAutoPtr` 같은 포인터를 저장 하는 각 개체와 같은 포인터를 두 번 삭제 될 가능성이 줄어듭니다.  
  
 `CAutoPtr`또한 대 한 포인터 컬렉션 생성을 단순화합니다. 컬렉션 클래스를 파생 하 고 소멸자를 재정의 하는 대신 더 간단 하 게의 컬렉션을 만드는 `CAutoPtr` 개체입니다. 컬렉션 삭제 되 면는 `CAutoPtr` 개체는 범위를 벗어나 자동으로 자체를 삭제 합니다.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) 변형으로 동일한 방식으로 작동 하 고 `CAutoPtr`점을 제외 하 고 이러한 메모리 할당 및 해제 하는 대신 c + + 다른 힙 함수를 사용 하 여 **새** 및 **삭제** 연산자입니다. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) 비슷합니다 `CAutoPtr`, 유일한 차이점은 사용 하 여 **벡터 new** 및 **벡터 delete** 를 할당 및 메모리를 해제 합니다.  
  
 참고 항목 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및 [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 배열 또는 스마트 포인터 목록을 필요한 경우.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&74;](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>CAutoPtr::Attach  
 이 메서드는 기존 포인터의 소유권을 호출 합니다.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 `CAutoPtr` 개체는이 포인터의 소유권을 갖게 됩니다.  
  
### <a name="remarks"></a>주의  
 때는 `CAutoPtr` 자동으로 삭제 하는 포인터 할당 된 모든 데이터 범위를 벗어나면, 개체 포인터의 소유권을 갖습니다. 경우 [CAutoPtr::Detach](#detach) 은 호출 프로그래머가 다시 모든 해제에 대 한 책임 지정 된 리소스가 할당 됩니다.  
  
 디버그 빌드에서 어설션 오류는 경우에 [CAutoPtr::m_p](#m_p) 데이터 멤버는 현재 기존 값을 가리킵니다; 즉,가 아닌 NULL로 합니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
##  <a name="cautoptr"></a>CAutoPtr::CAutoPtr  
 생성자입니다.  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 기존 포인터입니다.  
  
 `TSrc`  
 다른 관리 되는 형식 `CAutoPtr`현재 개체를 초기화 하는 데 사용 합니다.  
  
### <a name="remarks"></a>주의  
 `CAutoPtr` 는 기존 포인터를 사용 하 여 개체를 만들 수 있습니다,이 경우에 포인터 소유권 전송 합니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
##  <a name="dtor"></a>CAutoPtr:: ~ CAutoPtr  
 소멸자입니다.  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다. 호출 [CAutoPtr::Free](#free)합니다.  
  
##  <a name="detach"></a>CAutoPtr::Detach  
 포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 포인터의 복사본을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 포인터의 소유권을 해제, 설정 된 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수를 NULL, 포인터의 복사본을 반환 합니다. 호출한 후 **분리**를 해제 하 여 프로그래머의 몫 리소스가 할당 됩니다 매길는 `CAutoPtr` 개체 수 이전에 독자를 대상으로 reponsibility 합니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
##  <a name="free"></a>CAutoPtr::Free  
 가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CAutoPtr`합니다.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>주의  
 가 가리키는 개체는 `CAutoPtr` 해제 되 면 및 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수는 NULL로 설정 됩니다.  
  
##  <a name="m_p"></a>CAutoPtr::m_p  
 포인터 데이터 멤버 변수입니다.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수는 포인터 정보를 보유합니다.  
  
##  <a name="operator_eq"></a>CAutoPtr::operator =  
 대입 연산자입니다.  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 포인터입니다.  
  
 `TSrc`  
 클래스 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조를 반환 합니다.는 **CAutoPtr\< T >**합니다.  
  
### <a name="remarks"></a>주의  
 대입 연산자를 분리는 `CAutoPtr` 개체에서 모든 현재 포인터 새 포인터를 연결 하 고 `p`, 그 자리에 있습니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
##  <a name="operator_ptr"></a>CAutoPtr::operator-&gt;  
 멤버 포인터 연산자입니다.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 값을 반환 된 [CAutoPtr::m_p](#m_p) 데이터 멤버 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 연산자를 사용 하 여 가리키는 클래스에서 메서드를 호출 하는 `CAutoPtr` 개체입니다. 디버그 빌드에서 어설션 오류는 경우에 `CAutoPtr` NULL을 가리킵니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
##  <a name="operator_t_star"></a>CAutoPtr::operator T *  
 캐스트 연산자입니다.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>반환 값  
 클래스 템플릿에 정의 된 개체 데이터 형식에 대 한 포인터를 반환 합니다.  
  
### <a name="example"></a>예제  
 예제를 참조는 [CAutoPtr 개요](../../atl/reference/cautoptr-class.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr 클래스](../../atl/reference/cautovectorptr-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

