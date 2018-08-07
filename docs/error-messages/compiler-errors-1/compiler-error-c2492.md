---
title: 컴파일러 오류 C2492 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68b3d769c5b86be172a0a27828fb1dc3905959d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197366"
---
# <a name="compiler-error-c2492"></a>컴파일러 오류 C2492
'*변수*': 스레드 저장 기간이 있는 데이터에는 dll 인터페이스를 사용할 수 없습니다    
  
 으로 선언 된 변수는 [스레드](../../cpp/thread.md) 특성 및 DLL과 인터페이스입니다. 주소는 `thread` 변수 알 런타임까지 수 있으므로 한 DLL 가져오기 또는 내보내기에 연결할 수 없습니다.  
  
 다음 샘플에서는 C2492 오류가 생성 됩니다.  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```