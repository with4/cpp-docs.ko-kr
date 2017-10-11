---
title: "컴파일러 오류 C3755 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c302a3a0a417b8668d18c8329b083648cb28ccab
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3755"></a>컴파일러 오류 C3755
'delegate': 대리자를 정의할 수 없습니다.  
  
 A [대리자 (c + + 구성 요소 확장명)](../../windows/delegate-cpp-component-extensions.md) 선언할 수는 있지만 정의 되지 않았습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3755 오류가 발생 합니다.  
  
```  
// C3755.cpp  
// compile with: /clr /c  
delegate void MyDel() {};   // C3755  
```  
  
## <a name="example"></a>예제  
 C3755는 대리자 서식 파일을 만들려면 사용 하려는 경우에 발생할 수 있습니다. 다음 샘플에서는 C3755 오류가 발생 합니다.  
  
```  
// C3755_b.cpp  
// compile with: /clr /c  
ref struct R {  
   template<class T>  
   delegate void D(int) {}   // C3755  
};  
```
