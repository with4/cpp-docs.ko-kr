---
title: 컴파일러 오류 C2581 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2581
dev_langs:
- C++
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cb826519ad9137a0e980fd1734b57e8a715f438
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231196"
---
# <a name="compiler-error-c2581"></a>컴파일러 오류 C2581
'type': 정적 ' operator =' 함수가 잘못 되었습니다.  
  
 할당 (`=`) 연산자가 잘못 선언 되었습니다로 `static`합니다. 대입 연산자가 될 수 없습니다 `static`합니다. 자세한 내용은 참조 [사용자 정의 연산자 (C + + /cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2581 오류가 발생 합니다.  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```