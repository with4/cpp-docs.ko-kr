---
title: "컴파일러 경고 (수준 4) C4295 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1424302c5c109ff79f35c922d1e5051b15655554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4295"></a>컴파일러 경고(수준 4) C4295
  
> '*배열*': 배열이 너무 작아서 null 종결 문자를 포함 하려면  
  
 배열 초기화 되었지만 배열에서 마지막 문자; null이 아닙니다. 배열에 액세스 하면 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예  
  
 다음 샘플에서는 C4295 경고가 발생 합니다. 이 문제를 해결 하려면 선언할 수 있습니다는 배열 크기 종료 보유를 더 크게 이니셜라이저에서 null입니다.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```