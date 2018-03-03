---
title: "컴파일러 경고 (수준 4) C4295 | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="compiler-warning-level-4-c4295"></a>컴파일러 경고(수준 4) C4295
  
> '*배열*': 배열이 너무 작아서 null 종결 문자를 포함 하려면  
  
배열 초기화 되었지만 배열에서 마지막 문자; null이 아닙니다. 문자열 배열에 액세스 하면 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예  
  
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
