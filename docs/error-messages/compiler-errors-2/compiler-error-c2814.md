---
title: "컴파일러 오류 C2814 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2814"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2814"
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# 컴파일러 오류 C2814
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 네이티브 형식은 관리되는 형식 또는 WinRT 형식 'type' 내부에 중첩될 수 없습니다.  
  
## 예제  
 네이티브 형식은 CLR 또는 WinRT 형식에 중첩할 수 없습니다.  다음 샘플에서는 C2814 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
  
## 예제  
 Managed Extensions for C\+\+를 사용할 때는 [\_\_gc](../../misc/gc.md), [\_\_nogc](../../misc/nogc.md) 또는 [\_\_value](../../misc/value.md) 키워드 중 하나를 사용하여 포함된 형식의 "managed\-ness"를 명시적으로 지정해야 합니다.  
  
 다음 샘플에서는 C2814 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2814_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class A {  
   class B {};   // C2814  
   __gc class C {};   // OK  
};  
```