---
title: "컴파일러 경고 (수준 3) C4101 | Microsoft Docs"
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
  - "C4101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4101"
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' :참조되지 않은 지역 변수입니다.  
  
 지역 변수가 사용되지 않습니다.  이 경고는 명백한 상황에서 발생합니다.  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 하지만 이 경고는 **정적** 멤버 함수가 클래스의 인스턴스를 통해 호출되는 경우에도 발생합니다.  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 이러한 경우에는 컴파일러가 `si`에 대한 정보를 사용하여 **정적** 함수에 액세스하지만 **정적** 함수를 호출하는 데에는 클래스의 인스턴스가 필요하지 않으므로 경고가 발생합니다.  이 경고를 해결하려면 다음을 수행하십시오.  
  
-   컴파일러가 `func`에 대한 호출에서 `si`의 인스턴스를 사용할 수 있는 생성자를 추가합니다.  
  
-   `func` 정의에서 **static** 키워드를 제거합니다.  
  
-   **정적** 함수를 명시적으로 호출합니다. `int y = S::func();`