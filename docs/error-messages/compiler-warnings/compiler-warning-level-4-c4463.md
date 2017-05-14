---
title: "컴파일러 경고 (수준 4) C4463 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: 0
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
ms.openlocfilehash: 63f9c9172daffe11f91c521f514f0e8e53331b22
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4463"></a>컴파일러 경고 (수준 4) C4463  
  
> 오버플로. 할당 *값* 값만 포함할 수 있는 비트 필드에 *low_value* 를 *high_value*  
  
할당 된 *값* 비트 필드에서 보유할 수 있는 값의 범위를 벗어났습니다. 부호 있는 비트 필드 형식 상위 비트가 부호 비트를 사용 하면  *n*  는 부호 있는 비트 필드는-2 비트 필드 크기 범위<sup>n-1</sup> 2로<sup>n-1</sup>-1, 0에서 2 까지의 범위를 보유 하는 부호 없는 비트 필드<sup>n</sup>-1입니다.  
  
## <a name="example"></a>예제  
  
형식의 비트 필드에 값 3 할당 하려고 했기 때문에이 예제에서는 C4463 `int` 1-2에서 범위 크기가 2가 있습니다.  
  
이 문제를 해결 하려면 허용 되는 범위 내의 요소에 할당 된 값을 변경할 수 있습니다. 비트 필드는 0에서 3 사이에 부호 없는 값을 저장 하기 위한 개체를 선언 형식이 변경할 수 있습니다 `unsigned`합니다. 필드는 범위-4-3에 값을 보유할 경우 3 비트 필드 크기를 변경할 수 있습니다.  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  

