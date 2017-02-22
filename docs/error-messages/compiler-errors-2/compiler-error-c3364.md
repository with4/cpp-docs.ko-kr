---
title: "컴파일러 오류 C3364 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3364"
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delegate': 대리 생성자: 인수가 관리되는 클래스 또는 전역 함수의 멤버 함수에 대한 포인터여야 합니다.  
  
 대리 생성자의 둘째 매개 변수에는 멤버 함수 주소와 임의 클래스의 정적 멤버 함수 주소 중 하나를 사용합니다.  두 주소 모두 단순 주소로 처리됩니다.  
  
 다음 샘플에서는 C3364 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3364_2.cpp  
// compile with: /clr  
  
delegate int D( int, int );  
  
ref class C {  
public:  
   int mf( int, int ) {  
      return 1;  
   }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364  
  
   // try the following line instead  
   // System::Delegate^ pD = gcnew D(pC, &C::mf);  
}  
```  
  
 다음 샘플에서는 C3364 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3364.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__delegate int D(int, int);  
  
__gc class C {  
public:  
   int mf(int, int) {  
      return 1;  
   }  
};  
  
int main() {  
   C *pC = new C;  
   System::Delegate *pD = new D(pC, pC->mf(1, 2));   // C3364  
   // try the following line instead  
   // System::Delegate *pD = new D(pC, &C::mf);  
}  
```