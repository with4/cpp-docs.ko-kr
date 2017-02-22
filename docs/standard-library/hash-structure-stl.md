---
title: "hash 구조체(STL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "thread/std::hash"
dev_langs: 
  - "C++"
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# hash 구조체(STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

고유 하 게 하 여 결정 되는 값을 반환 하는 멤버 함수를 정의 `Val`합니다. 멤버 함수 정의 [해시](../standard-library/hash-class.md) 매핑 값 형식에 적합 한 함수 `thread::id` 인덱스 값의 분포에 있습니다.  
  
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
 **헤더:** 스레드  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\< 스레드>](../standard-library/thread.md)   
 [unary_function 구조체](../standard-library/unary-function-struct.md)
