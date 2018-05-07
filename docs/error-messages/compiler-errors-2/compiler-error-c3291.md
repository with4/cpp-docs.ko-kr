---
title: 컴파일러 오류 C3291 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 829479ce2514d77f5be99feae03edf056963af7c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3291"></a>컴파일러 오류 C3291
'default' : trivial 속성의 이름이 될 수 없습니다.  
  
 trivial 속성은 `default`로 이름을 바꿀 수 없습니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3291을 생성합니다.  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```