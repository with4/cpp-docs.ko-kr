---
title: "컴파일러 오류 C2506 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 200155978fe12a142519dd79e50cb409e9ea1e54
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2506"></a>컴파일러 오류 C2506
'member': '__declspec(modifier)'이 기호에 적용할 수 없습니다  
  
 관리 되는 클래스의 정적 멤버에 대 한 각 프로세스 또는 appdomain 별를 선언할 수 없습니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2506 오류가 발생 합니다.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```
