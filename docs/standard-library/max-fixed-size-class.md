---
title: "max_fixed_size 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: corob-msft
ms.author: corob
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 50c33d1ea29053ab3c5e76c5c02c22d799e06c6e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="maxfixedsize-class"></a>max_fixed_size 클래스
[freelist](../standard-library/freelist-class.md) 개체를 고정된 최대 길이로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <std::size_t Max>  
class max_fixed_size
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Max`|`freelist`에 저장할 요소의 최대 수를 결정하는 max 클래스입니다.|  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[max_fixed_size](#max_fixed_size)|`max_fixed_size` 형식의 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[allocated](#allocated)|할당된 메모리 블록의 수를 늘립니다.|  
|[deallocated](#deallocated)|할당된 메모리 블록의 수를 줄입니다.|  
|[full](#full)|사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.|  
|[released](#released)|사용 가능한 목록에서 메모리 블록의 수를 줄입니다.|  
|[saved](#saved)|사용 가능한 목록에서 메모리 블록의 수를 늘립니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="allocated"></a>  max_fixed_size::allocated  
 할당된 메모리 블록의 수를 늘립니다.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Nx`|증분 값입니다.|  
  
### <a name="remarks"></a>설명  
 멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 `cache_freelist::allocate`에서 `new` 연산자를 성공적으로 호출할 때마다 호출됩니다. `_Nx` 인수는 청크에서 `new` 연산자가 할당한 메모리 블록의 수입니다.  
  
##  <a name="deallocated"></a>  max_fixed_size::deallocated  
 할당된 메모리 블록의 수를 줄입니다.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`_Nx`|증분 값입니다.|  
  
### <a name="remarks"></a>설명  
 멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 `cache_freelist::deallocate`에서 `delete` 연산자를 호출할 때마다 호출됩니다. `_Nx` 인수는 청크에서 `delete` 연산자가 할당 취소한 메모리 블록의 수입니다.  
  
##  <a name="full"></a>  max_fixed_size::full  
 사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.  
  
```
bool full();
```  
  
### <a name="return-value"></a>반환 값  
 `Max <= _Nblocks`이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출에서 `true`를 반환하는 경우 `deallocate`는 메모리 블록을 사용 가능한 목록에 넣고, false를 반환하는 경우 `deallocate`는 `delete` 연산자를 호출하여 블록을 할당 취소합니다.  
  
##  <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size  
 `max_fixed_size` 형식의 개체를 생성합니다.  
  
```
max_fixed_size();
```  
  
### <a name="remarks"></a>설명  
 이 생성자는 저장된 값 `_Nblocks`를 0으로 초기화합니다.  
  
##  <a name="released"></a>  max_fixed_size::released  
 사용 가능한 목록에서 메모리 블록의 수를 줄입니다.  
  
```
void released();
```  
  
### <a name="remarks"></a>설명  
 저장된 값 `_Nblocks`를 줄입니다. 현재 [max 클래스](../standard-library/allocators-header.md)의 `released` 멤버 함수는 사용 가능한 목록에서 메모리 블록을 제거할 때마다 `cache_freelist::allocate`에서 호출됩니다.  
  
##  <a name="saved"></a>  max_fixed_size::saved  
 사용 가능한 목록에서 메모리 블록의 수를 늘립니다.  
  
```
void saved();
```  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 저장된 값 `_Nblocks`를 늘립니다. 이 멤버 함수는 사용 가능한 목록에 메모리 블록을 넣을 때마다 `cache_freelist::deallocate`에서 호출됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




