---
title: "컴파일러 경고 (수준 1) C4572 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4572"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4572"
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4572
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[ParamArray\] 특성은 \/clr에서 사용되지 않습니다. 대신 '...'을 사용하십시오.  
  
 이제는 사용되지 않는 스타일을 가변 인수 목록을 지정하는 데 사용했습니다.  CLR에 대한 컴파일 시 <xref:System.ParamArrayAttribute> 대신 가변 매개 변수\(...\) 구문을 사용해야 합니다.  자세한 내용은 [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4572 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```