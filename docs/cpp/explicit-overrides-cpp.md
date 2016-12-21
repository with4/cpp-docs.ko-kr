---
title: "명시적 재정의 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파생 클래스, 가상 함수"
  - "가상 함수 명시적 재정의"
  - "명시적 가상 함수 재정의"
  - "재정의, 함수"
  - "가상 함수, 명시적 재정의"
ms.assetid: ee583234-5cda-4e90-b55e-3f9fbf079ced
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 명시적 재정의 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 동일한 가상 함수가 두 개 이상의 [인터페이스](../cpp/interface.md)에 선언되었거나 클래스가 이러한 인터페이스에서 파생된 경우 각 가상 함수를 명시적으로 재정의할 수 있습니다.  
  
 새로운 관리되는 구문을 사용하는 관리 코드의 명시적 재정의에 대한 자세한 내용은 [명시적 재정의](../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 예제  
 다음 코드 예제에서는 명시적 재정의를 사용하는 방법을 보여 줍니다.  
  
```  
// deriv_ExplicitOverrides.cpp  
// compile with: /GR  
extern "C" int printf_s(const char *, ...);  
  
__interface IMyInt1 {  
   void mf1();  
   void mf1(int);  
   void mf2();  
   void mf2(int);  
};  
  
__interface IMyInt2 {  
   void mf1();  
   void mf1(int);  
   void mf2();  
   void mf2(int);  
};  
  
class CMyClass : public IMyInt1, public IMyInt2 {  
public:  
   void IMyInt1::mf1() {  
      printf_s("In CMyClass::IMyInt1::mf1()\n");  
   }  
  
   void IMyInt1::mf1(int) {  
      printf_s("In CMyClass::IMyInt1::mf1(int)\n");  
   }  
  
   void IMyInt1::mf2();  
   void IMyInt1::mf2(int);  
  
   void IMyInt2::mf1() {  
      printf_s("In CMyClass::IMyInt2::mf1()\n");  
   }  
  
   void IMyInt2::mf1(int) {  
         printf_s("In CMyClass::IMyInt2::mf1(int)\n");  
   }  
  
   void IMyInt2::mf2();  
   void IMyInt2::mf2(int);  
};  
  
void CMyClass::IMyInt1::mf2() {  
   printf_s("In CMyClass::IMyInt1::mf2()\n");  
}  
  
void CMyClass::IMyInt1::mf2(int) {  
   printf_s("In CMyClass::IMyInt1::mf2(int)\n");  
}  
  
void CMyClass::IMyInt2::mf2() {  
   printf_s("In CMyClass::IMyInt2::mf2()\n");  
}  
  
void CMyClass::IMyInt2::mf2(int) {  
   printf_s("In CMyClass::IMyInt2::mf2(int)\n");  
}  
  
int main() {  
   IMyInt1 *pIMyInt1 = new CMyClass();  
   IMyInt2 *pIMyInt2 = dynamic_cast<IMyInt2 *>(pIMyInt1);  
  
   pIMyInt1->mf1();  
   pIMyInt1->mf1(1);  
   pIMyInt1->mf2();  
   pIMyInt1->mf2(2);  
   pIMyInt2->mf1();  
   pIMyInt2->mf1(3);  
   pIMyInt2->mf2();  
   pIMyInt2->mf2(4);  
  
   // Cast to a CMyClass pointer so that the destructor gets called  
      CMyClass *p = dynamic_cast<CMyClass *>(pIMyInt1);  
      delete p;  
}  
```  
  
  **In CMyClass::IMyInt1::mf1\(\)**  
**In CMyClass::IMyInt1::mf1\(int\)**  
**In CMyClass::IMyInt1::mf2\(\)**  
**In CMyClass::IMyInt1::mf2\(int\)**  
**In CMyClass::IMyInt2::mf1\(\)**  
**In CMyClass::IMyInt2::mf1\(int\)**  
**In CMyClass::IMyInt2::mf2\(\)**  
**In CMyClass::IMyInt2::mf2\(int\)**   
## 참고 항목  
 [상속](../cpp/inheritance-cpp.md)