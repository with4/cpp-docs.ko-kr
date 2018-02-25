---
title: "iterator 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 274d472e3f3768a67a49ed6ca074f3a126bfd0fd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="iterator-struct"></a>iterator 구조체
사용자 정의 반복기 클래스가 **iterator_trait**에서 제대로 작동하도록 하기 위해 사용되는 빈 기본 구조체입니다.  
  
## <a name="syntax"></a>구문  
```    
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };  
```    
## <a name="remarks"></a>설명  
 템플릿 구조체는 모든 반복기에 대해 기본 형식으로 사용됩니다. 이 구조체는 멤버 형식을 정의합니다.  
  
- `iterator_category`(템플릿 매개 변수 `Category`의 동의어)  
  
- `value_type`(템플릿 매개 변수 **Type**의 동의어)  
  
- `difference_type`(템플릿 매개 변수 `Distance`의 동의어)  
  
- `distance_type`(템플릿 매개 변수 `Distance`의 동의어)  
  
- `pointer`(템플릿 매개 변수 `Pointer`의 동의어)  
  
- `reference`(템플릿 매개 변수 `Reference`의 동의어)  
  
 `value_type`은 **pointer**가 const **Type**의 개체를 가리키고 참조가 const **Type**의 개체를 지정하는 경우에도 상수 형식이 아니어야 합니다.  
  
## <a name="example"></a>예  
 반복기 기본 클래스에서 형식을 선언하고 사용하는 방법에 대한 예제는 [iterator_traits](../standard-library/iterator-traits-struct.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<iterator>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)



