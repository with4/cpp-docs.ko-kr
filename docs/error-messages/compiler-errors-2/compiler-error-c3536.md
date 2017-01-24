---
title: "컴파일러 오류 C3536 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3536"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3536"
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3536
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'기호': 초기화하기 전에는 사용할 수 없습니다.  
  
 지정된 기호는 초기화하기 전에 사용할 수 없습니다.  실제로 변수 자체를 사용하여 변수를 초기화할 수 없다는 의미입니다.  
  
### 이 오류를 해결하려면  
  
1.  변수 자체를 사용하여 변수를 초기화하지 마십시오.  
  
## 예제  
 다음 예제에서는 각 변수가 변수 자체를 사용하여 초기화되므로 C3536이 발생합니다.  
  
```  
// C3536.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto a = a;     //C3536  
   auto b = &b;    //C3536  
   auto c = c + 1; //C3536  
   auto* d = &d;   //C3536  
   auto& e = e;    //C3536  
   return 0;  
};  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)