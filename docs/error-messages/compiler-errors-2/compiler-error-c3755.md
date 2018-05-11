---
title: 컴파일러 오류 C3755 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3602f78659e58de9dc394f6887901c46de8de60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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