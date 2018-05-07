---
title: 컴파일러 오류 C3753 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3753
dev_langs:
- C++
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0d9cb2db2729e5ccb1787e2505fdf0aed1f7a12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3753"></a>컴파일러 오류 C3753
일반 속성을 사용할 수 없습니다.  
  
 제네릭 매개 변수 목록은 관리 되는 클래스, 구조체 또는 함수에만 사용할 수 있습니다.  
  
 자세한 내용은 참조 [제네릭](../../windows/generics-cpp-component-extensions.md) 및 [속성](../../windows/property-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3753 오류가 발생 합니다.  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```