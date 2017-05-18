---
title: "allocator_newdel 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators::allocator_newdel
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- allocator_newdel
- stdext::allocators::allocator_newdel
dev_langs:
- C++
helpviewer_keywords:
- allocator_newdel class
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 45a80316ddd36cccbe5e5aab6757163d45bc2f07
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="allocatornewdel-class"></a>allocator_newdel 클래스
`operator delete`를 사용하여 메모리 블록의 할당을 취소하고 `operator new`를 사용하여 메모리 블록을 할당하는 할당자를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Type>  
class allocator_newdel;
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Type`|할당자에 의해 할당된 요소 형식입니다.|  
  
## <a name="remarks"></a>설명  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) 매크로는 다음 문에서 이 클래스를 `name` 매개 변수로서 전달합니다. `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<allocators>  
  
 **네임스페이스:** stdext  
  
## <a name="see-also"></a>참고 항목  
 [\<allocators>](../standard-library/allocators-header.md)




