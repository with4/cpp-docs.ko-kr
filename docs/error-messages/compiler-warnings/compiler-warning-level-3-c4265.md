---
title: "컴파일러 경고 (수준 3) C4265 | Microsoft Docs"
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
  - "C4265"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4265"
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4265
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 클래스에 가상 함수가 있지만 소멸자는 가상이 아닙니다.  
  
 클래스에 가상 함수가 있지만 소멸자는 가상이 아닌 경우 클래스가 기본 클래스 포인터를 통해 소멸될 때 형식 개체는 제대로 소멸되지 않습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4265 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4265.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4265)  
class B  
{  
public:  
   virtual void vmf();  
  
   ~B();  
   // try the following line instead  
   // virtual ~B();  
};   // C4265  
  
int main()  
{  
   B b;  
}  
```