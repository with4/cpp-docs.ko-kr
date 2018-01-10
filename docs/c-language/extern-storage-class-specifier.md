---
title: "extern 저장소 클래스 지정자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 448a659afaf7a0251d500da3d9878d30550b9180
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="extern-storage-class-specifier"></a>extern 저장소 클래스 지정자
`extern` 저장소 클래스 지정자를 사용하여 선언된 변수는 프로그램 소스 파일의 외부 수준에서 정의된 것과 같은 이름이 지정된 변수에 대한 참조입니다. 내부 `extern` 선언은 블록 내에서 외부 수준 변수 정의를 표시하는 데 사용됩니다. 외부 수준에서 다른 방식으로 선언되지 않는 한 `extern` 키워드를 사용하여 선언된 변수는 자신이 선언된 블록에서만 표시됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 내부 및 외부 수준의 선언을 보여 줍니다.  
  
```  
// extern_StorageClassSpecified.c  
#include <stdio.h>  
  
void other( void );  
  
int main()  
{  
    // Reference to i, defined below:   
    extern int i;  
  
    // Initial value is zero; a is visible only within main:   
    static int a;  
  
    // b is stored in a register, if possible:   
    register int b = 0;  
  
    // Default storage class is auto:   
    int c = 0;  
  
    // Values printed are 1, 0, 0, 0:   
    printf_s( "%d\n%d\n%d\n%d\n", i, a, b, c );  
    other();  
    return;  
}  
  
int i = 1;  
  
void other( void )  
{  
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;  
  
    // i is redefined; global i no longer visible:   
    int i = 16;  
  
    // This a is visible only within the other function:   
    static int a = 2;  
  
    a += 2;  
    // Values printed are 16, 4, and 1:  
    printf_s( "%d\n%d\n%d\n", i, a, *external_i );  
}  
```  
  
 이 예제에서 `i` 변수는 초기 값 1로 외부 수준에서 정의됩니다. `extern` 함수의 `main` 선언은 외부 수준 `i`에 대한 참조를 선언하는 데 사용됩니다. 이니셜라이저가 생략되었으므로 **static** 변수 `a`가 기본적으로 0으로 초기화됩니다. `printf`에 대한 호출은 1, 0, 0 및 0 값을 출력합니다.  
  
 `other` 함수에서는 **static** 포인터 변수 `external_i`를 초기화하는 데 전역 변수 `i`의 주소가 사용됩니다. 전역 변수에 **static** 수명이 있으므로, 즉 해당 주소가 프로그램 실행 중 변경되지 않으므로 이것이 가능합니다. 다음으로 `i` 변수는 초기 값이 16인 지역 변수로 다시 정의됩니다. 이 재정의 작업은 해당 이름을 지역 변수에 사용하여 숨겨진 외부 수준 `i`의 값에 영향을 주지 않습니다. 이제 `i` 포인터를 통해 이 블록 내에서 간접적으로만 전역 `external_i`의 값에 액세스할 수 있습니다. **auto** 변수 `i`의 주소를 포인터에 할당할 수는 없습니다. 블록에 들어갈 때마다 달라질 수 있기 때문입니다. `a` 변수는 **static** 변수로 선언되고 2로 초기화됩니다. 내부 수준에서 **static** 변수는 이 변수가 선언된 블록 내에서만 표시되기 때문에 이 `a`는 `main`에 있는 `a`와 충돌하지 않습니다.  
  
 `a` 변수는 2씩 증가하여 4가 됩니다. `other` 함수가 동일한 프로그램에서 다시 호출될 경우 `a`의 초기 값은 4가 됩니다. 내부 **static** 변수는 프로그램이 종료 후 해당 변수가 선언된 블록에 다시 들어가도 값을 유지합니다.  
  
## <a name="see-also"></a>참고 항목  
 [내부 수준 선언에 대한 저장소 클래스 지정자](../c-language/storage-class-specifiers-for-internal-level-declarations.md)