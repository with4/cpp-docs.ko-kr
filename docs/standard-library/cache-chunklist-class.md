---
title: "cache_chunklist 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3d8047844a96cf80e64ab7aae5d1e7d9f4a85474
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="cachechunklist-class"></a>cache_chunklist 클래스
단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Sz`|할당할 배열의 요소 수입니다.|  
  
## <a name="remarks"></a>설명  
 이 템플릿 클래스는 `operator new`를 사용하여 원시 메모리의 청크를 할당하고, 필요한 경우 메모리 블록에 대한 저장소를 할당할 블록을 하위 할당합니다. 또한 각 청크에 대한 별도의 사용 가능한 목록에 할당 취소된 메모리 블록을 저장하고, 사용 중인 메모리 블록이 없는 청크의 경우 `operator delete`를 사용하여 할당 취소합니다.  
  
 각 메모리 블록은 `Sz` 바이트의 사용 가능한 메모리 및 해당 블록이 속해 있는 청크에 대한 포인터를 포함합니다. 각 청크는 `operator new`와 `operator delete`에서 필요로 하는 `Nelts` 메모리 블록, 세 가지 포인터, int 및 데이터를 포함합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 형식의 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[allocate](#allocate)|메모리 블록을 할당합니다.|  
|[deallocate](#deallocate)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="allocate"></a>  cache_chunklist::allocate  
 메모리 블록을 할당합니다.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`count`|할당할 배열의 요소 수입니다.|  
  
### <a name="return-value"></a>반환 값  
 할당된 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist  
 `cache_chunklist` 형식의 개체를 생성합니다.  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="deallocate"></a>  cache_chunklist::deallocate  
 지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|저장소에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|  
|`count`|저장소에서 할당을 취소할 개체의 수입니다.|  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




