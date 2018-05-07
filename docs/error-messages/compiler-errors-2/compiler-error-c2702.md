---
title: 컴파일러 오류 C2702 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2702
dev_langs:
- C++
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 813833b5c3aeb7da0651fecb879ac12ca0713d13
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2702"></a>컴파일러 오류 C2702
__except 나타나지 않을 수 있습니다 종료 블록에  
  
 예외 처리기 (`__try`/`__except`) 안에 중첩 될 수 없습니다는 `__finally` 블록입니다.  
  
 다음 샘플에서는 C2702 오류가 생성 됩니다.  
  
```  
// C2702.cpp  
// processor: x86 IPF  
int Counter;  
int main() {  
   __try {}  
   __finally {  
      __try {}   // C2702  
      __except( Counter ) {}   // C2702  
   }  
}  
```