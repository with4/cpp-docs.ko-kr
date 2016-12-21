---
title: "컴파일러 오류 C2252 | Microsoft Docs"
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
  - "C2252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2252"
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 범위에서 템플릿을 명시적으로 인스턴스화할 수 없습니다.  
  
 컴파일러가 템플릿의 명시적 인스턴스화에 대한 문제를 감지했습니다.  예를 들어, 함수에서 템플릿을 명시적으로 인스턴스화할 수 없습니다.  
  
 다음 샘플에서는 C2252 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```