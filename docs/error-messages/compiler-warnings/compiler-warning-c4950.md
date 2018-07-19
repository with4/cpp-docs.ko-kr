---
title: 컴파일러 경고 C4950 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55221cc233c74e612dd4a521641be90a6dbf9314
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272027"
---
# <a name="compiler-warning-c4950"></a>컴파일러 경고 C4950
'type_or_member': 사용되지 않는 것으로 표시되었습니다.  
  
사용 되지 않음으로 표시 된 멤버 또는 형식이 고 <xref:System.ObsoleteAttribute> 특성입니다.  
  
C4950은 항상 오류로 실행됩니다. 사용 하 여이 경고를 해제할 수 있습니다는 [경고](../../preprocessor/warning.md) pragma 지시문 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C4950을 생성합니다.  
  
```cpp  
// C4950.cpp  
// compile with: /clr  
using namespace System;  
  
// Any reference to Func3 should generate an error with message  
[System::ObsoleteAttribute("Will be removed in next version", true)]  
Int32 Func3(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt3 = ::Func3(2, 2);   // C4950  
}  
```