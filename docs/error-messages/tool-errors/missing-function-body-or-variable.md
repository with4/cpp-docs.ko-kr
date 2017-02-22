---
title: "함수 본문 또는 변수 누락 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수 본문"
  - "변수, 없음"
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 함수 본문 또는 변수 누락
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수 프로토타입을 사용하면 컴파일러가 오류 발생 없이 작업을 계속할 수 있지만, 예약된 변수 공간이나 함수 코드가 없으므로 링커가 주소에 대한 호출을 확인할 수 없습니다.  링커가 반드시 확인해야 하는 함수에 대한 호출을 만들면 이 오류가 발생합니다.  
  
## 예제  
 main에서 함수를 호출하면 컴파일러는 프로토타입에 따라 함수가 있는 것으로 간주하므로 LNK2019가 발생합니다.  링커는 함수를 찾지 못합니다.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## 예제  
 C\+\+에서는 클래스에 대해 특정 함수를 구현해야 하며 클래스 정의에 프로토타입을 포함하지 말아야 합니다.  헤더 파일 외부에서 클래스를 정의하는 경우에는 클래스 이름이 함수 앞에 와야 합니다\(`Classname``::``memberfunction`\).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## 참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)