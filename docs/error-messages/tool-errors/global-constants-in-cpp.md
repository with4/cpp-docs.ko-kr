---
title: "C++의 전역 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상수, global"
  - "전역 상수"
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++의 전역 상수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 전역 상수에는 정적 링크가 포함된다는 점에서  C\+\+와 C는 다릅니다.  여러 파일에서 C\+\+의 전역 상수를 사용하려고 하면 확인할 수 없는 외부 오류가 발생합니다.  컴파일러는 전역 상수를 최적화하여 변수에 대한 공간을 예약해 두지 않습니다.  
  
 이 오류를 해결하기 위한 방법 중 하나로 함수 프로토타입에서와 마찬가지로, 필요한 경우 헤더 파일에 const 초기화를 포함한 다음 이 헤더를 CPP 파일에 포함할 수 있습니다.  변수를 비상수로 만든 다음 이에 액세스할 때 상수 참조를 사용해도 됩니다.  
  
 다음 샘플에서는 C2019 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 두 번째 코드 파일:  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## 참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)