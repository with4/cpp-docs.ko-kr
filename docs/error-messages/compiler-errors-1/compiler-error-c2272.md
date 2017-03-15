---
title: "컴파일러 오류 C2272 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2272"
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 정적 멤버 함수에 한정자를 사용할 수 없습니다.  
  
 `static` 멤버 함수가 메모리 모델 지정자\(예: [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md)\) 및 `static` 멤버 함수에 사용할 수 없는 메모리 모델 한정자를 사용하여 선언되었습니다.  
  
 다음 샘플에서는 C2272 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```