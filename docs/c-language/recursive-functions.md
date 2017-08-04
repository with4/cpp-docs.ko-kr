---
title: "재귀 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 38d98e568b88d8b26be2a04a9b643fb0d99a9712
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="recursive-functions"></a>재귀 함수
C 프로그램의 모든 함수를 재귀적으로 호출할 수 있습니다. 즉, 함수가 자신을 호출할 수 있습니다. 재귀적 호출 수는 스택의 크기로 제한됩니다. 스택 크기를 설정하는 링커 옵션에 대한 자세한 내용은 [/STACK(스택 할당)](../build/reference/stack-stack-allocations.md)(/STACK) 링크 옵션을 참조하세요. 함수가 호출될 때마다 완료되지 않은 이전 호출의 값이 덮어쓰이지 않도록 새로운 저장소가 매개 변수와 **auto** 및 **register** 변수에 대해 할당됩니다. 매개 변수는 생성된 함수의 인스턴스에 의해서만 직접 액세스될 수 있습니다. 이전 매개 변수는 함수의 다음 인스턴스에 의해 직접 액세스될 수 없습니다.  
  
 **static** 저장소로 선언된 변수에는 재귀적 호출 시마다 새로운 저장소가 필요하지 않습니다. 해당 저장소는 프로그램 수명 동안 존재합니다. 이러한 변수에 대한 각 참조는 동일한 저장소 영역에 액세스합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 재귀적 호출을 보여 줍니다.  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [함수 호출](../c-language/function-calls.md)
