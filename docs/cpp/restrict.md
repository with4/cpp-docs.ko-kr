---
title: "__restrict | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__restrict"
  - "__restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__restrict 키워드[C++]"
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 포인터 형식을 반환하는 함수 선언 또는 정의에 적용되며, 함수가 다른 포인터를 사용하여 별칭이 지정되지 않을 개체를 반환함을 컴파일러에 알립니다.  
  
## 구문  
  
```  
__declspec(restrict) return_type f();  
```  
  
## 설명  
 컴파일러는 `__declspec(restrict)`를 전파합니다.  예를 들어 CRT `malloc` 함수는 `__declspec(restrict)`로 데코레이팅되므로 `malloc`를 사용하여 메모리 위치로 초기화된 포인터도 별칭이 지정되지 않습니다.  
  
 컴파일러는 포인터가 실제로 별칭이 지정되지 않았는지 확인하지 않습니다.  프로그램에서 `restrict __declspec` 한정자로 표시된 포인터에 별칭을 지정하지 않도록 확인하는 것은 개발자의 책임입니다.  
  
 변수에 대한 유사한 의미 체계를 보려면 [\_\_restrict](../cpp/extension-restrict.md)를 참조하십시오.  
  
## 예제  
 `restrict`를 사용하는 예제를 보려면 [noalias](../cpp/noalias.md)를 참조하십시오.  
  
 C\+\+ AMP의 일부인 restrict 키워드에 대한 자세한 내용은 [restrict \(C\+\+ AMP\)](../cpp/restrict-cpp-amp.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)