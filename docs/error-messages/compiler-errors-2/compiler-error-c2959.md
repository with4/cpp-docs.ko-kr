---
title: 컴파일러 오류 C2959 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2959
dev_langs:
- C++
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce13a340812bce7cd6e5a0e4f8b2601b530fd3a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2959"></a>컴파일러 오류 C2959
제네릭 클래스 또는 함수는 서식 파일의 구성원이 아닐 수 있습니다.  
  
 자세한 내용은 참조 [Windows 런타임 및 관리 되는 템플릿](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) 및 [제네릭](../../windows/generics-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2959 오류가 발생 합니다.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```