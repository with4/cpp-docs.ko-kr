---
title: "컴파일러 경고 (수준 1) C4162 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4162"
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : C 링크가 있는 함수가 없습니다.  
  
 C 링크가 있는 함수가 선언되었지만 찾을 수 없습니다.  
  
 이 경고를 해결하려면 C 컴파일러를 호출하여 .c 파일에서 컴파일합니다.  C\+\+ 컴파일러를 호출해야만 하는 경우 함수 선언 앞에 extern "C"를 배치합니다.  
  
 다음 샘플에서는 C4162 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```