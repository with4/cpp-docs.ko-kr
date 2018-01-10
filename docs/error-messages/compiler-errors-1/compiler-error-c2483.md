---
title: "컴파일러 오류 C2483 | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2483
dev_langs: C++
helpviewer_keywords: C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f7f9f30724c02d44e054bf16ff1460370c30e06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2483"></a>컴파일러 오류 C2483

>'*식별자*': '스레드' 생성자 또는 소멸자가 있는 개체를 선언할 수 없습니다.

이 오류 메시지는 Visual Studio 2015 이상 버전에서 사용 되지 않습니다. 이전 버전에서 사용 하 여 변수 선언에서 `thread` 특성 생성자 나 런타임에 계산에 필요한 다른 식으로 초기화할 수 없습니다. 정적 식 초기화에 필요 `thread` 데이터입니다.

## <a name="example"></a>예

다음 샘플에서는 Visual Studio 2013 및 이전 버전에서 C2483 오류가 발생 합니다.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error  

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>참고 항목

[thread](../../cpp/thread.md)