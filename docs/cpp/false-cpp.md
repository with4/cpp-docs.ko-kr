---
title: false (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- false_cpp
dev_langs:
- C++
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b45db3a1226a9069c03ff928227a8719c83eb65
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406522"
---
# <a name="false-c"></a>false (C++)
키워드를 사용 하면 형식의 변수에 대 한 두 값 중 하나인 [bool](../cpp/bool-cpp.md) 조건식 (조건식은 이제는 **true** 부울 식). 예를 들어 경우 `i` 형식의 변수가 **bool**의 `i = false;` 문 할당 **false** 를 `i`합니다.  
  
## <a name="example"></a>예  
  
```cpp 
// bool_false.cpp  
#include <stdio.h>  
  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
```Output  
1  
0  
```  
  
## <a name="see-also"></a>참고자료  
 [키워드](../cpp/keywords-cpp.md)