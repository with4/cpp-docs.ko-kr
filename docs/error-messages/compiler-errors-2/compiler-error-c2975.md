---
title: "컴파일러 오류 C2975 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f779ec2623b6b07f61c1e8347304288d0bcfe96a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2975"></a>컴파일러 오류 C2975

> '*인수*': 템플릿 인수가 잘못 되었습니다 '*형식*', 컴파일 타임 상수 식이 필요 합니다.

템플릿 인수 템플릿 선언; 일치 하지 않습니다. 상수 식 꺾쇠 괄호 안에 표시 됩니다. 변수는 템플릿 실제 인수로 허용 되지 않습니다. 템플릿 정의를 확인하여 올바른 형식을 찾습니다.

## <a name="example"></a>예

다음 샘플에서는 c2975 경고가 발생 하 고 올바른 사용법을 보여 줍니다.

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975도 발생 합니다. 사용 하는 경우 #95; &#95; 줄 &#95; #95 컴파일 타임 상수와 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)합니다. 문제를 해결할 수로 컴파일하여 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 대신 **/ZI**합니다.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```