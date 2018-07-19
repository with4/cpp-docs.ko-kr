---
title: 컴파일러 경고 (수준 3) C4390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d052a1fa6124aa1518cddec00566e14668fe111d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290090"
---
# <a name="compiler-warning-level-3-c4390"></a>컴파일러 경고(수준 3) C4390
';': 제어 된 빈 문이 반환 합니다. 이 의도 무엇입니까?  
  
 명령이 없는 제어문 후 세미콜론을 찾았습니다.  
  
 매크로 인해 C4390를 얻게 하는 경우 사용 해야는 [경고](../../preprocessor/warning.md) pragma를 C4390 매크로 포함 하는 모듈에서 사용 하지 않도록 합니다.  
  
 다음 샘플에서는 C4390 오류가 생성 됩니다.  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```