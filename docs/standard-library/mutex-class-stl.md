---
title: "mutex 클래스(STL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::mutex"
dev_langs: 
  - "C++"
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# mutex 클래스(STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*mutex type* 을 나타냅니다.  이 형식의 객체는 프로그램내에서 상호 배제를 시행하기위해 사용될 수 있습니다.  
  
## 구문  
  
```  
class mutex;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[mutex::mutex 생성자\(STL\)](../Topic/mutex::mutex%20Constructor%20\(STL\).md)|`mutex` 개체를 생성합니다.|  
|[mutex::~mutex 소멸자\(STL\)](../Topic/mutex::~mutex%20Destructor%20\(STL\).md)|`mutex` 객체에 의해 사용된 리소스를 모두 해제합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[mutex::lock 메서드\(STL\)](../Topic/mutex::lock%20Method%20\(STL\).md)|스레드가 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|  
|[mutex::native\_handle 메서드\(STL\)](../Topic/mutex::native_handle%20Method%20\(STL\).md)|mutex 핸들을 나타내는 특정한 구현 형식을 반환합니다.|  
|[mutex::try\_lock 메서드\(STL\)](../Topic/mutex::try_lock%20Method%20\(STL\).md)|차단되지 않고 `mutex`의 소유권을 가져오려고 시도합니다.|  
|[mutex::unlock 메서드\(STL\)](../Topic/mutex::unlock%20Method%20\(STL\).md)|`mutex`의 소유권을 해제합니다.|  
  
## 요구 사항  
 **헤더:** mutex  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)