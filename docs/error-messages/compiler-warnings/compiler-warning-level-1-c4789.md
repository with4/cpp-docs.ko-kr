---
title: "컴파일러 경고 (수준 1) C4789 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4789
dev_langs:
- C++
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fde48ccbcf3a4ddec6884ac9e0c259739954772
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4789"></a>컴파일러 경고(수준 1) C4789
버퍼 'identifier'(크기: N바이트)이(가) 오버런됩니다. M바이트가 오프셋 L부터 쓰입니다.  
  
 특정 CRT(C 런타임) 함수가 사용되고 매개 변수가 전달되고 할당이 수행되는 경우 컴파일 시간에 데이터 크기를 알 수 있도록 버퍼 오버런에 대해 경고합니다. 이 경고는 일반적인 데이터 크기 불일치 검색을 방지할 수 있는 상황에 사용됩니다.  
  
 이 경고는 컴파일 시간에 길이를 알 수 있는 데이터를 복사하여 컴파일 시간에 크기가 데이터에 비해 너무 작은 것을 알 수 있는 데이터 블록에 넣을 때 나타납니다.  복사는 다음 CRT 함수 중 하나의 내장 형식을 사용하여 수행해야 합니다.  
  
-   [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)  
  
-   [memset](../../c-runtime-library/reference/memset-wmemset.md)  
  
-   [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)  
  
 또한 이 경고는 캐스트를 사용하여 매개 변수 데이터 형식이 일치하지 않는 경우 lvalue 참조에서 할당을 복사하려고 하면 나타납니다.  
  
 Visual C++에서는 실행되지 않는 코드 경로에 대해 이 경고를 생성할 수 있습니다. 다음 예제와 같이 `#pragma`를 사용하여 이 경고를 일시적으로 비활성화할 수 있습니다.  
  
 `#pragma(push)`  
  
 `#pragma warning ( disable : 4789 )`  
  
 `// unused code that generates compiler warning C4789`  
  
 `#pragma(pop)`  
  
 이렇게 하면 Visual C++에서 특정 코드 블록에 대해 경고를 생성하지 않습니다. `#pragma(push)`는 `#pragma warning(disable: 4789)`에서 변경하기 전까지 기존 상태를 유지합니다. `#pragma(pop)`는 푸시된 상태를 복원하고 `#pragma warning(disable:4789)`의 효과를 제거합니다. C + + 전처리기 지시문에 대 한 자세한 내용은 `#pragma`, 참조 [경고](../../preprocessor/warning.md) 및 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4789를 생성합니다.  
  
```  
// C4789.cpp  
// compile with: /Oi /W1 /c  
#include <string.h>  
#include <stdio.h>  
  
int main()   
{  
    char a[20];  
    strcpy(a, "0000000000000000000000000\n");   // C4789  
  
    char buf2[20];  
    memset(buf2, 'a', 21);   // C4789  
  
    char c;  
    wchar_t w = 0;  
    memcpy(&c, &w, sizeof(wchar_t));  
}  
```  
  
## <a name="example"></a>예  
 또한 다음 샘플에서는 C4789를 생성합니다.  
  
```  
// C4789b.cpp  
// compile with: /W1 /O2 /c  
// processor: x86  
short G;  
  
void main()  
{  
   int * p = (int *)&G;   
   *p = 3;   // C4789 - writes an int through a pointer to short  
}   
```