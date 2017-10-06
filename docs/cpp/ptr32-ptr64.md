---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
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
ms.openlocfilehash: d722f8403efbe1172fefbe8a792c95d4063e893f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Microsoft 전용  
 `__ptr32`는 32비트 시스템의 네이티브 포인터를 나타내는 반면 `__ptr64`는 64비트 시스템의 네이티브 포인터를 나타냅니다.  
  
 다음 예제에서는 이러한 포인터 형식 각각을 선언하는 방법을 보여 줍니다.  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 32비트 시스템에서 `__ptr64`로 선언한 포인터는 32비트 포인터로 잘립니다. 64비트 시스템에서 `__ptr32`로 선언한 포인터는 64비트 포인터로 강제 변환됩니다.  
  
> [!NOTE]
>  사용할 수 없습니다 `__ptr32` 또는 `__ptr64` 로 컴파일할 때 **/clr: pure**합니다. 그렇지 않으면 `Compiler Error C2472`가 생성됩니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `__ptr32` 및 `__ptr64` 키워드로 포인터를 선언 및 할당하는 방법을 보여 줍니다.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
```Output  
32  
64  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [기본 형식](../cpp/fundamental-types-cpp.md)
