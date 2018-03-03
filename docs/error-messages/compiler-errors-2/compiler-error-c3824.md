---
title: "컴파일러 오류 C3824 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e18e20cb1ffbe6d06060b3001c48f01b8b8b8cbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3824"></a>컴파일러 오류 C3824
'member':이 형식은이 컨텍스트 (함수 매개 변수, 반환 형식 또는 정적 멤버)에 나타날 수 없습니다  
  
 고정 포인터는 함수 매개 변수, 반환 형식 수 없습니다 또는 선언 된 `static`합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3824 오류가 생성 됩니다.  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
