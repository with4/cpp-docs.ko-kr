---
title: "컴파일러 경고 (수준 1) C4743 | Microsoft Docs"
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
  - "C4743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4743"
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'*type*'의 크기가 '*file1*'과\(와\) '*file2*'에서 서로 다릅니다\(*number*바이트, *number*바이트\).  
  
 두 파일에서 참조하거나 정의한 외부 변수가 해당 파일에서 서로 다른 형식이고, *file1*의 변수 크기가 *file2*의 변수 크기와 다르다는 것을 컴파일러에서 확인했습니다.  
  
 C\+\+의 경우 중요한 상황에서 이 경고가 발생할 수 있습니다.  서로 다른 두 파일에서 이름이 같은 동일한 형식을 선언하는 경우, 이러한 선언에 가상 함수가 포함된 경우 및 이 선언이 동일하지 않은 경우 컴파일러는 가상 함수 테이블에 대해 C4744 경고를 표시할 수 있습니다.  이 경고는 동일한 형식에 대해 크기가 서로 다른 두 개의 가상 함수 테이블이 있고 링커가 이 둘 중 하나를 실행 파일에 통합하기 위해 선택해야 하기 때문에 발생합니다.  이 경우 프로그램에서 잘못된 가상 함수를 호출할 수 있습니다.  
  
 이 경고를 해결하려면 형식이나 변수에 서로 다른 이름을 사용하거나 동일한 형식 정의를 사용해야 합니다.  
  
## 예제  
 다음 샘플에는 한 가지 형식 정의가 포함되어 있습니다.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## 예제  
 다음 샘플에서는 C4743 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```