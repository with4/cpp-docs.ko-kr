---
title: 컴파일러 오류 C2423 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2423
dev_langs:
- C++
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96408323c7afd9e15fee521c9d20005dfc6da21
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195856"
---
# <a name="compiler-error-c2423"></a>컴파일러 오류 C2423
'number': 잘못 된 크기 조정  
  
 인라인 어셈블리 코드 레지스터 크기를 조정 하려면 1, 2, 4 또는 8 이외의 번호를 사용 합니다.  
  
 다음 샘플에서는 C2423 오류가 생성 됩니다.  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```