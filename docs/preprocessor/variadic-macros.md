---
title: Variadic 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5918c7d91a3568799f361fcb42edb2e9c7b1445e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850537"
---
# <a name="variadic-macros"></a>Variadic 매크로
Variadic 매크로 가변 개수의 인수를 포함 하는 함수 형식 매크로입니다.  
  
## <a name="remarks"></a>설명  
 Variadic 매크로 사용 하려면 줄임표로 지정할 수 있습니다 매크로 정의와 대체 식별자에 마지막 형식 인수 `__VA_ARGS__` 불필요 한 인수를 삽입 하려면 정의에 사용할 수 있습니다.  `__VA_ARGS__` 쉼표로 구분 하를 포함 하 여 줄임표와 일치 하는 인수를 모두으로 바뀝니다.  
  
 C 표준 지정 하나 이상의 인수에 매크로 후행 쉼표는 식으로 해결 되지 않으면 되도록 줄임표에 전달 되어야 합니다.  줄임표 전달 되는 인수가 없는 경우 Visual c + + 구현 후행 쉼표를 표시 되지 것입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## <a name="output"></a>출력  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
```  
  
## <a name="see-also"></a>참고 항목  
 [매크로(C/C++)](../preprocessor/macros-c-cpp.md)