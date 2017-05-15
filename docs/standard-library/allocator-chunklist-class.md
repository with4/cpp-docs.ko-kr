---
title: "allocator_chunklist 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::allocators::allocator_chunklist
- allocators::allocator_chunklist
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
- allocator_chunklist
dev_langs:
- C++
helpviewer_keywords:
- allocator_chunklist class
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9acdadca2530f8ed54ec4bde7a6a1fe218f00f8a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="allocatorchunklist-class"></a>allocator_chunklist 클래스
[cache_chunklist](../standard-library/cache-chunklist-class.md) 유형의 캐시를 사용하여 개체에 대한 저장소 할당 및 해제를 관리하는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Type>  
class allocator_chunklist;
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Type`|할당자에 의해 할당된 요소 형식입니다.|  
  
## <a name="remarks"></a>설명  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 문에서 이 클래스를 `name` 매개 변수로서 전달합니다. `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist``);`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




