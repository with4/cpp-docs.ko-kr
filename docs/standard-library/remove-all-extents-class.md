---
title: "remove_all_extents 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::remove_all_extents
dev_langs:
- C++
helpviewer_keywords:
- remove_all_extents class
- remove_all_extents
ms.assetid: 548dc536-82e7-423a-b8c1-443d66d9632e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d527deeeaea38bb57d9edf32d7325b1684ea8a5c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="removeallextents-class"></a>remove_all_extents 클래스
배열 형식에서 배열이 아닌 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>
struct remove_all_extents;

template <class T>  
using remove_all_extents_t = typename remove_all_extents<T>::type;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 `remove_all_extents<T>` 인스턴스는 모든 배열 차원이 제거된 배열 형식 `T`의 요소 형식인 수정된 형식을 보관하고, `T`가 배열 형식이 아닌 경우 `T`를 보관합니다.  
  
## <a name="example"></a>예  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_all_extents<int> == "   
        << typeid(std::remove_all_extents_t<int>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5]> == "   
        << typeid(std::remove_all_extents_t<int[5]>).name()   
        << std::endl;   
    std::cout << "remove_all_extents_t<int[5][10]> == "   
        << typeid(std::remove_all_extents_t<int[5][10]>).name()   
        << std::endl;   
  
    return (0);   
    }  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_extent 클래스](../standard-library/remove-extent-class.md)
