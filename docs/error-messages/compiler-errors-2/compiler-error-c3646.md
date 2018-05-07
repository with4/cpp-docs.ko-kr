---
title: 컴파일러 오류 C3646 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad0a7f16b54d2a06586bdb4c26c87dbcf9ae7b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3646"></a>컴파일러 오류 C3646
'specifier': 알 수 없는 재정의 지정자  
  
 컴파일러가 위치는 재정의 지정자를 찾을 것으로 예상 했지만 토큰을 컴파일러에서 인식할 수 없습니다 위치에 토큰을 찾았습니다.  
  
 자세한 내용은 참조 [재정의 지정자](../../windows/override-specifiers-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3646 오류가 생성 됩니다.  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```