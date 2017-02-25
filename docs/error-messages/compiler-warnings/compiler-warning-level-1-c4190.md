---
title: "컴파일러 경고 (수준 1) C4190 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4190"
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1'에 C 링크를 지정했으나 C와 호환되지 않는 UDT 'identifier2'을\(를\) 반환합니다.  
  
 함수 또는 함수에 대한 포인터가 UDT\(클래스, 구조체, 열거형, 공용 구조체 또는 [\_\_value](../../misc/value.md) 형식 등의 사용자 정의 형식\)를 반환 형식 및 `extern` "C" 링크로 사용하지만,  다음과 같은 경우에는 사용할 수 없습니다.  
  
-   이 함수에 대한 모든 호출이 C\+\+에서 발생하는 경우  
  
-   함수가 C\+\+로 정의된 경우  
  
## 예제  
  
```  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```