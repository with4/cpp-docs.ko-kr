---
title: "컴파일러 경고 (수준 1) C4350 | Microsoft Docs"
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
  - "C4350"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4350"
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4350
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동작 변경: 'member1'이\(가\) 'member2' 대신 호출됩니다.  
  
 비상수 참조에 rvalue를 바인딩할 수 없습니다.  이전 버전의 Visual C\+\+에서는 직접 초기화를 통해 비상수 참조에 rvalue를 바인딩할 수 있었습니다.  새 버전에서는 이러한 코드를 사용하면 경고가 발생합니다.  
  
 이전 버전과의 호환성을 위해 비상수 참조에 rvalue를 계속 바인딩할 수는 있지만 가능한 한 표준 규칙을 따르는 것이 좋습니다.  
  
 이 경고는 Visual C\+\+ .NET 2002 컴파일러와 달리 변경된 동작을 나타냅니다.  이 경고를 활성화하면 올바른 코드가 제시됩니다.  예를 들어, **std::auto\_ptr** 클래스 템플릿을 사용하는 경우 이 경고가 표시될 수 있습니다.  
  
 이 경고가 발생하면 코드를 조사하여 비상수 참조에 rvalue가 바인딩되어 있는지 확인합니다.  문제를 해결하려면 참조에 상수를 추가하거나 상수 참조 오버로드를 추가로 제공해야 합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4350 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```