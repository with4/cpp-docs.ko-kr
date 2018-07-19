---
title: 컴파일러 오류 C2498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2498
dev_langs:
- C++
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c50596e4e5ca47a0f1bdf3f5ab25405139b66447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196612"
---
# <a name="compiler-error-c2498"></a>컴파일러 오류 C2498
'function': 'novtable' 클래스 선언 또는 정의에 적용 될 수 있습니다  
  
 이 오류를 사용 하 여 발생할 수 있습니다 `__declspec(novtable)` 함수를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2498 오류가 생성 됩니다.  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```