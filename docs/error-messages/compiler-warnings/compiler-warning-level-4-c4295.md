---
title: "컴파일러 경고 (수준 4) C4295 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: b831b8e7b838ef25679d49a132c66d4b378fdcd7
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4295"></a>컴파일러 경고(수준 4) C4295
  
> '*배열*': 배열이 너무 작아서 null 종결 문자를 포함 하려면  
  
 배열 초기화 되었지만 배열에서 마지막 문자; null이 아닙니다. 배열에 액세스 하면 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
  
 다음 샘플에서는 C4295 경고가 발생 합니다. 이 문제를 해결 하려면 선언할 수 있습니다는 배열 크기 종료 보유를 더 크게 이니셜라이저에서 null입니다.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```
