---
title: 컴파일러 경고 (수준 4) C4201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4201
dev_langs:
- C++
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56805506c112d0d92b627b905199bcbbeae8d2f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4201"></a>컴파일러 경고(수준 4) C4201
비표준 확장이 사용 됨: 이름이 없는 구조체/공용 구조체  
  
 Microsoft 확장 (/Ze)에서는 다른 구조체 또는 공용 구조체의 멤버로 선언 자 없이 구조체를 지정할 수 있습니다. ANSI 규격 오류를 생성 하는 이러한 구조 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>예제  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```