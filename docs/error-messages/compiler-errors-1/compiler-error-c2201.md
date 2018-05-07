---
title: 컴파일러 오류 C2201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2201
dev_langs:
- C++
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eea410297cdb8deb45c4376f8736234ad8f69699
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2201"></a>컴파일러 오류 C2201
'identifier': 가져오거나 내보내려면 외부 링크가 있어야 합니다  
  
 내보낸된 식별자는 `static`합니다.  
  
 다음 샘플에서는 C2286을 생성합니다.  
  
```  
// C2201.cpp  
// compile with: /c  
__declspec(dllexport) static void func() {}   // C2201 func() is static  
__declspec(dllexport) void func2() {}   // OK  
```  
  
## <a name="see-also"></a>참고 항목  
 [링크 형식](../../cpp/types-of-linkage.md)