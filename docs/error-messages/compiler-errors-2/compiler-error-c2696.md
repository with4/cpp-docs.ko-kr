---
title: "컴파일러 오류 C2696 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2696"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2696"
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2696
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 형식 'type'의 임시 개체를 만들 수 없습니다.  
  
 관리되지 않는 프로그램에서 `const`를 참조하면 컴파일러가 생성자를 호출하며 스택에 임시 개체를 만듭니다.  그러나 관리되는 클래스는 스택에서 만들 수 없습니다.  
  
 C2696은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C2696 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2696b.cpp  
// compile with: /clr:oldSyntax  
  
__gc class G {  
public:  
   G( int i ) {}  
};  
  
void func( const G& g );  
  
int main() {  
   func( 1 );   // C2696  
   G *myG = new G( 1 );   // OK  
   func( *myG );  
}  
```