---
title: "컴파일러 오류 C2492 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68268be94897e3c648e95185877dec9e276355c4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
