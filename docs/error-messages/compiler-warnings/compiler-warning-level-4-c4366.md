---
title: "컴파일러 경고 (수준 4) C4366 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4366"
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 컴파일러 경고 (수준 4) C4366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단항 'operator' 연산자의 결과가 맞춰지지 않을 수 있습니다.  
  
 압축으로 인해 구조체 멤버를 맞출 수 없는 경우 컴파일러는 맞춰진 포인터에 멤버의 주소를 할당할 때 이 사실을 경고 메시지로 알립니다.  기본적으로 모든 포인터가 맞춰집니다.  
  
 C4366을 해결하려면 구조체의 맞춤을 변경하거나 [\_\_unaligned](../../cpp/unaligned.md) 키워드를 사용하여 포인터를 선언해야 합니다.  
  
 자세한 내용은 \_\_unaligned 및 [pack](../../preprocessor/pack.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4366 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```