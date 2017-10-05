---
title: "&lt;forward_list&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 6696f42d2ba7cb6daabb8f2ff38093911838c1ca
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 함수
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 두 정방향 목록의 요소를 교환합니다.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `left.swap(right)`를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [<forward_list>](../standard-library/forward-list.md)




