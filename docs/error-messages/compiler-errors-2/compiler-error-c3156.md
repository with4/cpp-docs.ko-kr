---
title: "컴파일러 오류 c 3156 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3156
dev_langs:
- C++
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 793b143fa42e790610a086782c4bf99369965e1f
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3156"></a>컴파일러 오류 c 3156
'class': 관리되는 또는 WinRT 형식의 지역 정의를 사용할 수 없습니다.  
  
 함수에 관리되는 또는 WinRT 클래스, 구조체 또는 인터페이스의 정의 또는 선언을 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3156를 생성합니다.  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  

