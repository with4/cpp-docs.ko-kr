---
title: 컴파일러 오류 C3909 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3909
dev_langs:
- C++
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53e89dd422b1289d926ab04a0f17ae4d6185d19d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3909"></a>컴파일러 오류 C3909
WinRT 또는 관리 되는 형식 발생 해야 aWinRT 또는 관리 되는 이벤트 선언  
  
 Windows 런타임 이벤트 또는 관리되는 이벤트가 네이티브 형식으로 선언되었습니다. 이 오류를 해결하려면 Windows 런타임 형식 또는 관리되는 형식으로 이벤트를 선언합니다.  
  
 자세한 내용은 참조 [이벤트](../../windows/event-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3909를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```