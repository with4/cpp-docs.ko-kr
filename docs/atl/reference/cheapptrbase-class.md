---
title: "CHeapPtrBase 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8084104489f6f1e2358ce0cbb573f4e20a0c4fce
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrbase-class"></a>CHeapPtrBase 클래스
이 클래스는 여러 힙 스마트 포인터 클래스에 대 한 기본을 형성 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 힙에 저장 될 개체 형식입니다.  
  
 `Allocator`  
 사용 하 여 메모리 할당 클래스입니다. 기본적으로 CRT 루틴은 메모리 할당 및 해제 하는 데 사용 됩니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|메모리를 할당 하려면이 메서드를 호출 합니다.|  
|[CHeapPtrBase::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|  
|[CHeapPtrBase::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|  
|[CHeapPtrBase::Free](#free)|가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CHeapPtrBase`합니다.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|캐스트 연산자입니다.|  
|[CHeapPtrBase::operator / /](#operator_amp)|연산자 < /.|  
|[-> CHeapPtrBase::operator](#operator_ptr)|멤버 포인터 연산자입니다.|  

  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|포인터 데이터 멤버 변수입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 여러 힙 스마트 포인터 클래스에 대 한 기본을 형성 합니다. 예를 들어 파생된 클래스에서 [CHeapPtr](../../atl/reference/cheapptr-class.md) 및 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), 자신의 생성자 및 연산자를 추가 합니다. 구현 예제에 대 한 이러한 클래스를 참조 하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes  
 메모리를 할당 하려면이 메서드를 호출 합니다.  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 할당할 메모리의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 True를 반환 하는 메모리는 성공적으로 할당, false 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 디버그 빌드에서 어설션 오류는 경우에 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수는 현재 기존 값을 가리킵니다; 즉,가 아닌 NULL로 합니다.  
  
##  <a name="attach"></a>CHeapPtrBase::Attach  
 이 메서드는 기존 포인터의 소유권을 호출 합니다.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pData`  
 `CHeapPtrBase` 개체는이 포인터의 소유권을 갖게 됩니다.  
  
### <a name="remarks"></a>주의  
 때는 `CHeapPtrBase` 자동으로 삭제 하는 포인터 할당 된 모든 데이터 범위를 벗어나면, 개체 포인터의 소유권을 갖습니다.  
  
 디버그 빌드에서 어설션 오류는 경우에 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수는 현재 기존 값을 가리킵니다; 즉,가 아닌 NULL로 합니다.  
  
##  <a name="dtor"></a>CHeapPtrBase:: ~ CHeapPtrBase  
 소멸자입니다.  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="detach"></a>CHeapPtrBase::Detach  
 포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 포인터의 복사본을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 포인터의 소유권을 해제, 설정 된 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수를 NULL, 포인터의 복사본을 반환 합니다.  
  
##  <a name="free"></a>CHeapPtrBase::Free  
 가 가리키는 개체를 삭제 하려면이 메서드를 호출 하는 `CHeapPtrBase`합니다.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>주의  
 가 가리키는 개체는 `CHeapPtrBase` 해제 되 면 및 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수는 NULL로 설정 됩니다.  
  
##  <a name="m_pdata"></a>CHeapPtrBase::m_pData  
 포인터 데이터 멤버 변수입니다.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수는 포인터 정보를 보유합니다.  
  
##  <a name="operator_amp"></a>CHeapPtrBase::operator&amp;  
 연산자 < /.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>반환 값  
 가 가리키는 개체의 주소를 반환 하는 `CHeapPtrBase` 개체입니다.  
  

##  <a name="operator_ptr"></a>CHeapPtrBase::operator-&gt;  

 멤버 포인터 연산자입니다.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 값을 반환 된 [CHeapPtrBase::m_pData](#m_pdata) 멤버 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 연산자를 사용 하 여 가리키는 클래스에서 메서드를 호출 하는 `CHeapPtrBase` 개체입니다. 디버그 빌드에서 어설션 오류는 경우에 `CHeapPtrBase` NULL을 가리킵니다.  
  
##  <a name="operator_t_star"></a>CHeapPtrBase::operator T *  
 캐스트 연산자입니다.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>주의  
 반환 [CHeapPtrBase::m_pData](#m_pdata)합니다.  
  
##  <a name="reallocatebytes"></a>CHeapPtrBase::ReallocateBytes  
 메모리를 다시 할당 하려면이 메서드를 호출 합니다.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 바이트에 할당할 메모리의 새 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 True를 반환 하는 메모리는 성공적으로 할당, false 그렇지 않은 경우.  
  
## <a name="see-also"></a>참고 항목  
 [CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

