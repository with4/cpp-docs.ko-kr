---
title: "hash 구조체(C++ 표준 라이브러리)| Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 599560617d55c32de25775d74dcf27240994c36b
ms.lasthandoff: 02/24/2017

---
# <a name="hash-structure-c-standard-library"></a>hash 구조체(C++ 표준 라이브러리)
`Val`에 의해 고유하게 결정되는 값을 반환하는 멤버 함수를 정의합니다. 멤버 함수는 `thread::id` 형식의 값을 인덱스 값의 분포에 매핑하는 데 적합한 [hash](../standard-library/hash-class.md) 함수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** thread  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)   
 [unary_function 구조체](../standard-library/unary-function-struct.md)

