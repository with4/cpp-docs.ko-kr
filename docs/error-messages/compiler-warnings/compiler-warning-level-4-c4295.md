---
title: 컴파일러 경고 (수준 4) C4295 | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 815a669bc359121b13b1d636009cad81dc332304
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296304"
---
# <a name="compiler-warning-level-4-c4295"></a>컴파일러 경고(수준 4) C4295
  
> '*배열*': 배열이 너무 작아서 null 종결 문자를 포함 하려면  
  
배열 초기화 되었지만 배열에서 마지막 문자; null이 아닙니다. 문자열 배열에 액세스 하면 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 C4295 경고가 발생 합니다. 이 문제를 해결 하려면 선언할 수 있습니다는 배열 크기 보유를 더 크게 이니셜라이저 문자열 또는 있습니다 종료 null 배열을 이것은 의도 되지 않은 있도록 배열 이니셜라이저 목록을 사용할 수 `char`를 null로 끝나는 문자열이 아닙니다.  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
