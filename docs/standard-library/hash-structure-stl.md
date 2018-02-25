---
title: "hash 구조체(C++ 표준 라이브러리)| Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d14ee7900fe3c83097e0241859d9b569562736fb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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
 **헤더:** \<스레드 >  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)   
 [unary_function 구조체](../standard-library/unary-function-struct.md)
