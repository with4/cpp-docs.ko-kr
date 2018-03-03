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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d084e04e90c7fce9756e72a8b19d566ee829287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2506"></a>컴파일러 오류 C2506
'member': '__declspec(modifier)'이 기호에 적용할 수 없습니다  
  
 관리 되는 클래스의 정적 멤버에 대 한 각 프로세스 또는 appdomain 별를 선언할 수 없습니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 를 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2506 오류가 발생 합니다.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```