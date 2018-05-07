---
title: 컴파일러 오류 C2871 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2871
dev_langs:
- C++
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3aae5cc8200599b5f6b0643f07cbd342ec7d47c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2871"></a>컴파일러 오류 C2871
'name':이 이름의 네임 스페이스가 없습니다.  
  
네임 스페이스를 하지 않은 식별자를 전달 하는 경우이 오류가 발생 합니다는 [를 사용 하 여](../../cpp/namespaces-cpp.md#using_directives) 지시문입니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C2871 오류가 생성 됩니다.  
  
```cpp  
// C2871.cpp  
// compile with: /c
namespace a {
   int fn(int i) { return i; }
} 
namespace b { 
   using namespace d;   // C2871 because d is not a namespace  
   using namespace a;   // OK
}  
```