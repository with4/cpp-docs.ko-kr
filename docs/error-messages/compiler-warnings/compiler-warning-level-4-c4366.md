---
title: 컴파일러 경고 (수준 4) C4366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12410a567cb55d6dea74b8e5e595009e56b1071f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293704"
---
# <a name="compiler-warning-level-4-c4366"></a>컴파일러 경고(수준 4) C4366
단항 'operator' 연산자의 결과 정렬 되지 않을 수 있습니다.  
  
 구조체 멤버 수 없는 정렬 된 압축으로 인해, 하는 경우 컴파일러에서 경고가 표시 때 구성원의 주소는 정렬 된 포인터에 할당 됩니다. 기본적으로 모든 포인터는 정렬 됩니다.  
  
 C4366를 해결 하려면 중 하나는 구조체의 맞춤을 변경 하거나 사용 하 여 포인터를 선언에서 [__unaligned](../../cpp/unaligned.md) 키워드입니다.  
  
 자세한 내용은 참조 __unaligned 및 [팩](../../preprocessor/pack.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c 4366 합니다.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```