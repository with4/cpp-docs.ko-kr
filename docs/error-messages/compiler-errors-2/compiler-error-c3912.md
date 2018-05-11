---
title: 컴파일러 오류 C3912 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3912
dev_langs:
- C++
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9a5f392500b47771c6f19cc38d2fa2b5e679935
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3912"></a>컴파일러 오류 C3912
'event': 형식 이벤트의 대리자 형식 이어야 합니다.  
  
 이벤트 선언 된 했지만 올바른 형식의 했습니다.  
  
 자세한 내용은 참조 [이벤트](../../windows/event-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3912 오류가 생성 됩니다.  
  
```  
// C3912.cpp  
// compile with: /clr  
delegate void H();  
ref class X {  
   event int Ev;   // C3912  
   event H^ Ev2;   // OK  
};  
```