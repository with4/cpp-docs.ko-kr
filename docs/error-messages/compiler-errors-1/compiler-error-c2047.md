---
title: 컴파일러 오류 C2047 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2047
dev_langs:
- C++
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16aed5b8100a3591fcdfbb4451a76db51a5f3b4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164481"
---
# <a name="compiler-error-c2047"></a>컴파일러 오류 C2047
기본값이 잘못되었습니다.  
  
 `default` 키워드는 `switch` 문에만 나타날 수 있습니다.  
  
 다음 샘플에서는 C2047을 생성합니다.  
  
```  
// C2047.cpp  
int main() {  
   int i = 0;  
   default:   // C2047  
   switch(i) {  
      case 0:  
      break;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C2047b.cpp  
int main() {  
   int i = 0;  
   switch(i) {  
      case 0:  
      break;  
      default:  
      break;  
   }  
}  
```