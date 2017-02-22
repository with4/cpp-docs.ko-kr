---
title: "컴파일러 오류 C2825 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2825"
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var : '::'가 뒤에 나오면 클래스 또는 네임스페이스여야 합니다.  
  
 정규화된 이름을 만들지 못했습니다.  
  
 예를 들어, 사용자 코드에 함수 이름이 ::으로 시작되는 함수 선언을 포함하지 말아야 합니다.  
  
## 예제  
 다음 샘플에서는 C2825 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```