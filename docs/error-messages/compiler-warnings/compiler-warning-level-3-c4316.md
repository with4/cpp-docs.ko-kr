---
title: 컴파일러 경고 (수준 3) C4316 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 609f3bbe9f338c5d53491190512ce2b9c290cdb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298384"
---
# <a name="compiler-warning-level-3-c4316"></a>컴파일러 경고 (수준 3) C4316
이 형식에 대 한 힙에 할당 된 개체를 정렬할 수 있습니다.  
  
 사용 하 여 할당 된 과도 하 게 정렬 된 개체 `operator new` 지정 된 맞춤을 사용할 수 없습니다. 재정의 [new 연산자](../../c-runtime-library/operator-new-crt.md) 및 [delete 연산자](../../c-runtime-library/operator-delete-crt.md) 에 대 한 과도 하 게 정렬 된 형식 맞춤된 할당 루틴을 사용할 수 있도록-예를 들어 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 및 [_aligned_free](../../c-runtime-library/reference/aligned-free.md)합니다. 다음 샘플에서는 C4316 오류가 생성 됩니다.  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```