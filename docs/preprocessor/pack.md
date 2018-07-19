---
title: 팩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- pack_CPP
- vc-pragma.pack
dev_langs:
- C++
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c29c31cae2b7de59d4db5ed6546ad4eda6baecf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843628"
---
# <a name="pack"></a>pack
구조체, 공용 구조체 및 클래스 멤버에 대한 압축 맞춤을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## <a name="remarks"></a>설명  
 클래스를 압축하는 것은 해당 멤버를 메모리에서 서로 바로 뒤에 두는 것입니다. 이는 일부 또는 모든 멤버가 대상 아키텍처의 기본 맞춤보다 작은 경계에 정렬될 수 있음을 의미할 수 있습니다. `pack`은 데이터 선언 수준에서 제어 기능을 제공합니다. 이 컴파일러 옵션 점에서 차이가 [/Zp](../build/reference/zp-struct-member-alignment.md), 모듈 수준 제어 기능만 제공 합니다. `pack`은 pragma가 표시된 후 첫 번째 `struct`, `union` 또는 `class` 선언에서 적용됩니다. `pack`은 정의에 아무런 영향을 주지 않습니다. 호출 `pack` 없는 인수 집합으로 `n` 컴파일러 옵션에 설정 된 값에 **/Zp**합니다. 컴파일러 옵션이 설정되지 않은 경우 기본값은 8입니다.  
  
 구조체의 맞춤을 변경하는 경우 메모리에서 그만큼의 공간을 사용하지 않을 수 있지만, 성능이 저하되거나 정렬되지 않은 액세스에 대해 하드웨어에서 생성된 예외가 발생할 수도 있습니다.  사용 하 여이 예외 동작을 수정할 수 [SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621)합니다.  
  
 **표시** (선택 사항)  
 압축 맞춤에 대한 현재 바이트 값을 표시합니다. 경고 메시지에 값이 표시됩니다.  
  
 **푸시** (선택 사항)  
 내부 컴파일러 스택에 있는 현재 압축 맞춤 값을 푸시하고 현재 압축 맞춤 값을 `n`으로 설정합니다. `n`을 지정하지 않으면 현재 압축 맞춤 값이 푸시됩니다.  
  
 **pop** (선택 사항)  
 내부 컴파일러 스택의 맨 위에서 레코드를 제거합니다. 경우 `n` 으로 지정 하지 않으면 **pop**, 스택의 맨 위에 있는 결과 레코드와 연결 된 압축 값은 새로운 압축 맞춤 값입니다. `n`이 지정된 경우(예: `#pragma pack(pop, 16)`) `n`은 새로운 압축 맞춤 값이 됩니다. `identifier`를 사용하여 팝하는 경우(예: `#pragma pack(pop, r1)`) `identifier`가 있는 레코드를 찾을 때까지 스택의 모든 레코드가 팝됩니다. 해당 레코드가 팝되고 스택 맨 위에 있는 결과 레코드와 연결된 압축 값이 새로운 압축 맞춤 값이 됩니다. 사용 하 여 팝 하는 경우는 `identifier` 스택의 모든 레코드에 없는 하는 경우 **pop** 는 무시 됩니다.  
  
 `identifier`(선택 사항)  
 와 함께 사용할 경우 **푸시**, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 경우 **pop**, 될 때까지 내부 스택에서 레코드를 팝 `identifier` 가 제거 `identifier` 에 없는 내부 스택에서 아무 것도 팝 합니다.  
  
 `n`(선택 사항)  
 압축에 사용할 값(바이트)을 지정합니다. 하는 경우 컴파일러 옵션 [/Zp](../build/reference/zp-struct-member-alignment.md) 모듈에 대 한 기본값을 설정 하지 않으면 `n` 8입니다. 유효한 값은 1, 2, 4, 8 및 16입니다. 멤버의 맞춤은 `n`의 배수나 멤버 크기의 배수 중 작은 것의 경계에 있습니다.  
  
 `#pragma pack(pop, identifier, n)` 정의 되지 않습니다.  
  
 맞춤을 수정하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [__alignof](../cpp/alignof-operator.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [구조체 맞춤 예제](../build/examples-of-structure-alignment.md) (x64 전용)  
  
    > [!WARNING]
    >  Visual Studio 2015 이상에서는 `__alignof` 및 `declspec( align )`와 달리 컴파일러 간에 이식 가능한 표준 alignas 및 alignof 연산자를 사용할 수 있습니다. C++ 표준에서는 압축을 처리하지 않으므로 대상 아키텍처의 단어 크기보다 작은 맞춤을 지정하려면 여전히 `pack` 또는 해당 확장(다른 컴파일러)을 사용해야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 `pack` pragma를 사용하여 구조체의 맞춤을 변경하는 방법을 보여 줍니다.  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 사용 하는 **푸시**, **pop**, 및 **표시** 구문입니다.  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)