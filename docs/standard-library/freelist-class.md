---
title: "freelist 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7e4e636045d91cfaa4bc9532344cf73e68cec911
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="freelist-class"></a>freelist 클래스
메모리 블록의 목록을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Sz`|할당할 배열의 요소 수입니다.|  
|`Max`|사용 가능 목록에 저장할 최대 요소 수를 나타내는 최대 클래스입니다. 최대 클래스는 [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) 또는 [max_variable_size](../standard-library/max-variable-size-class.md)가 될 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 템플릿 클래스는 `Max`에 전달된 최대 클래스를 통해 결정된 목록의 최대 길이를 사용하여 크기가 `Sz`인 메모리 블록의 목록을 관리합니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[freelist](#freelist)|`freelist` 형식의 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[pop](#pop)|사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.|  
|[push](#push)|목록에 메모리 블록을 추가합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
##  <a name="freelist"></a>  freelist::freelist  
 `freelist` 형식의 개체를 생성합니다.  
  
```
freelist();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="pop"></a>  freelist::pop  
 사용 가능 목록에서 첫 번째 메모리 블록을 제거합니다.  
  
```
void *pop();
```  
  
### <a name="return-value"></a>반환 값  
 목록에서 제거된 메모리 블록의 포인터를 반환합니다.  
  
### <a name="remarks"></a>설명  
 목록이 비어 있으면 멤버 함수는 `NULL`을 반환합니다. 그렇지 않으면 목록에서 첫 번째 메모리 블록을 제거합니다.  
  
##  <a name="push"></a>  freelist::push  
 목록에 메모리 블록을 추가합니다.  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ptr`|사용 가능 목록에 추가할 메모리 블록의 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 최대 클래스의 `full` 함수가 `false`를 반환하면 `true`이고, 그렇지 않으면 `push` 함수가 `false`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 최대 클래스의 `full` 함수가 `false`를 반환하면 이 멤버 함수는 `ptr`가 가리키는 메모리 블록을 목록의 시작 부분에 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




