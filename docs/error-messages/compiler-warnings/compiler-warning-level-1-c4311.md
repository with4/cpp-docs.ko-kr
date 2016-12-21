---
title: "컴파일러 경고 (수준 1) C4311 | Microsoft Docs"
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
  - "C4311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4311"
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : 'type'에서 'type'\(으\)로 포인터가 잘립니다.  
  
 이 경고는 64비트 포인터 잘림 문제를 검색합니다.  예를 들어 코드가 64비트 아키텍처에 대해 컴파일된 경우 포인터\(64비트\)의 값을 `int`\(32비트\)에 할당하면 값이 잘립니다.  자세한 내용은 [포인터 사용 규칙](http://msdn.microsoft.com/library/windows/desktop/aa384242)을 참조하세요.  
  
 C4311 경고의 일반적인 원인에 대한 자세한 내용은 [일반적인 컴파일러 오류](http://msdn.microsoft.com/library/windows/desktop/aa384160)를 참조하세요.  
  
 다음 코드 예제는 64비트 대상에 대해 컴파일할 경우 C4311 경고가 발생하며, 해결 방법을 보여 줍니다.  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```