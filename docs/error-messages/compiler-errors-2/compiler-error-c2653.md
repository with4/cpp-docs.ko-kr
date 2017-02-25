---
title: "컴파일러 오류 C2653 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2653"
  - "CDaoRecordset 클래스, 레코드 추가"
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 클래스 또는 네임스페이스 이름이 아닙니다.  
  
 구문에 클래스, 구조체, 공용 구조체 또는 네임스페이스 이름이 필요합니다.  
  
 다음 샘플에서는 C2653 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2653.cpp  
// compile with: /c  
class yy {  
   void func1(int i);  
};  
  
void xx::func1(int m) {}   // C2653  
void yy::func1(int m) {}   // OK  
```  
  
 C2653은 복합 네임스페이스를 정의할 때에도 발생할 수 있습니다. C\+\+에서는 복합 네임스페이스를 사용할 수 없습니다.  
  
```  
// C2653b.cpp  
namespace a::b {int i;}   // C2653  
  
namespace a {  
   namespace b {  
      int i;  
   }  
}  
  
int main() {  
   a::b::i = 2;  
}  
```