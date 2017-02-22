---
title: "컴파일러 오류 C2217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2217"
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute1'에는 'attribute2'이\(가\) 있어야 합니다.  
  
 첫 번째 함수 특성에는 두 번째 특성이 필요합니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  중단 함수\(`__interrupt`\)가 `near`로 선언되었습니다.  중단 함수는 `far`여야 합니다.  
  
2.  중단 함수를 `__stdcall` 또는 `__fastcall`을 사용하여 선언했습니다.  중단 함수는 C 호출 규칙을 사용해야 합니다.  
  
## 예제  
 C2217은 가변 인수를 사용하는 CLR 함수에 대리자를 바인딩하려고 하는 경우에도 발생할 수 있습니다.  함수에 e 매개 변수 배열 오버로드도 있는 경우 이 오버로드를 대신 사용하십시오.  다음 샘플에서는 C2217 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```