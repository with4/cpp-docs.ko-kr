---
title: "컴파일러 오류 C3824 | Microsoft Docs"
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
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3824"
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 이 형식은 이 컨텍스트\(함수 매개 변수, 반환 형식 또는 정적 멤버\)에 사용할 수 없습니다.  
  
 고정 포인터는 함수 매개 변수, 반환 형식 또는 선언된 `static`이 될 수 없습니다.  
  
 다음 샘플에서는 C3824 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
  
 **Managed Extensions for C\+\+**  
  
 `__pin` 키워드를 사용하여 선언한 지역 포인터는 `static` 포인터로 선언할 수 없으며 내부 포인터가 될 수 없습니다.  
  
 다음 샘플에서는 C3824 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3824b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc struct A {};  
  
void func() {  
   static A __pin* a;   // C3824  
   A __pin* b;   // OK  
}  
```