---
title: "컴파일러 오류 C3154 | Microsoft Docs"
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
  - "C3154"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3154"
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3154
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가변 매개 변수\(...\) 앞에 ','가 필요합니다.매개 변수 배열 함수에서는 쉼표로 분리되지 않은 가변 매개 변수\(...\)를 사용할 수 없습니다.  
  
 가변 인수 함수가 잘못 선언되었습니다.  
  
 자세한 내용은 [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3154 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3154.cpp  
// compile with: /clr  
ref struct R {  
   void Func(int ... array<int> ^);   // C3154  
   void Func2(int i, ... array<int> ^){}   // OK  
   void Func3(array<int> ^){}   // OK  
   void Func4(... array<int> ^){}   // OK  
};  
  
int main() {  
   R ^ r = gcnew R;  
   r->Func4(1,2,3);  
}  
```