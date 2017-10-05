---
title: true (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- true_cpp
- "true"
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b10cf33ff93a01347ee8c8e7fc56bb5be8058f3a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="true-c"></a>true (C++)
## <a name="syntax"></a>구문  
  
```  
  
      bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## <a name="remarks"></a>설명  
 이 키워드는 형식의 변수에 대 한 두 값 중 하나 [bool](../cpp/bool-cpp.md) 조건식 (조건식은 true 부울 식이 이제). 경우 `i` 유형의 `bool`, then 문 `i = true;` 할당 **true** 를 `i`합니다.  
  
## <a name="example"></a>예제  
  
```  
// bool_true.cpp  
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
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)
