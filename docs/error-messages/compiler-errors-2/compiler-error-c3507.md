---
title: 컴파일러 오류 C3507 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3507
dev_langs:
- C++
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 008267fddbd1d83574081d7b257e6627b32a1f58
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252919"
---
# <a name="compiler-error-c3507"></a>컴파일러 오류 C3507
ProgID 'id'; 개 이하의 39 자의 가질 수 있습니다. 와 별개로 문장 부호를 포함 합니다. '.'; 또는 숫자로 시작  
  
 [progid](../../windows/progid.md) 특성에 사용할 수 있는 값에 대 한 제한이 있습니다.  
  
 다음 샘플에서는 C3507 오류가 생성 됩니다.  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```