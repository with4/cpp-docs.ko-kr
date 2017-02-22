---
title: "컴파일러 오류 C2847 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2847"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2847"
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2847
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT 또는 관리되는 형식 'class'에 sizeof를 적용할 수 없습니다.  
  
 [sizeof](../../cpp/sizeof-operator.md) 연산자는 컴파일 타임에 개체의 값을 가져옵니다.  WinRT 또는 관리되는 클래스, 인터페이스 또는 값 형식의 크기는 동적이므로 컴파일 타임에 알 수 없습니다.  
  
 예를 들어 다음 샘플에서는 C2847 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  
  
 다음 샘플에서는 C2847 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2847_b.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A *xA = new A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```