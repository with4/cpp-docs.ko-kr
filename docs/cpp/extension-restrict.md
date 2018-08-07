---
title: __restrict | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1ed49662b28f2ac84fc8c53f677b2deada974d3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403507"
---
# <a name="restrict"></a>__restrict
같은 **__declspec ( [제한](../cpp/restrict.md) )** 한정자를 **__restrict** 키워드 기호가 현재 범위에 별칭이 지정 아님을 나타냅니다. 합니다 **__restrict** 에서 다른 키워드는 `__declspec ( restrict )` 다음과 같이 한정자:  
  
-   합니다 **__restrict** 키워드는 변수 에서만 유효 하 고 `__declspec ( restrict )` 함수 선언 및 정의에 유효 합니다.  
  
-   **__restrict** 비슷합니다 **제한할** C99 사양의 있지만 **__restrict** c + + 또는 C 프로그램에서 사용할 수 있습니다.  
  
-   때 **__restrict** 는 사용 컴파일러 전파 하지 것입니다 변수의 별칭 없음 속성입니다. 즉, 할당 하는 경우는 **__restrict** 아닌 변수 **__restrict** 변수, 컴파일러는 여전히 사용할 수는 __restrict가 아닌 변수에 별칭이 지정 되도록 합니다. 동작은 다릅니다 합니다 **제한** C99 사양의 키워드입니다.  
  
 일반적으로 전체 함수의 동작을 변경하려면 키워드보다는 `__declspec ( restrict )`를 사용하는 것이 효율적입니다.  
  
 Visual Studio 2015 이상에서는 **__restrict** c + + 참조에 사용할 수 있습니다.  
  
> [!NOTE]
>  변수 또한를 사용 하는 경우는 [volatile](../cpp/volatile-cpp.md) 키워드 **volatile** 우선 적용 됩니다.  
  
## <a name="example"></a>예  
  
```cpp 
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>참고자료  
 [키워드](../cpp/keywords-cpp.md)