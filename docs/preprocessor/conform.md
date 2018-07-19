---
title: 준수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b145225cfed3131b406d15827b589aed718d16bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843745"
---
# <a name="conform"></a>준수
**C + + 전용**  
  
 런타임 동작을 지정 된 [/zc: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
 수정할 컴파일러 옵션의 이름을 지정합니다. 유일한 유효 *이름* 은 `forScope`합니다.  
  
 **표시** (선택 사항)  
 현재 설정을 사용 하면 *이름* (true 또는 false) 컴파일하는 동안 경고 메시지를 통해 표시 됩니다. 예를 들어, `#pragma conform(forScope, show)`을 입력합니다.  
  
 **사용 안 함**(선택 사항)  
 설정 *이름* 를 **에** 수 있도록는 [/zc: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션입니다. 기본값은 **오프**합니다.  
  
 **푸시** (선택 사항)  
 현재 값을 푸시합니다 *이름* 내부 컴파일러 스택으로 합니다. 지정 하는 경우 *식별자*를 지정할 수 있습니다는 **에** 또는 **오프** 값에 대 한 *이름* 스택으로 푸시 하도록 합니다. 예를 들어, `#pragma conform(forScope, push, myname, on)`을 입력합니다.  
  
 **pop** (선택 사항)  
 값을 설정 *이름* 내부 컴파일러 스택의 및 다음 스택 팝의 맨 위쪽에 있는 값에 있습니다. 식별자가 지정 된 경우 **pop**, 스택 인 레코드를 찾을 때까지 다시 팝 됩니다 *식별자*,에 대 한 현재 값이 있는 팝 됩니다 *이름* 에서 스택의 다음 레코드에 대 한 새 값이 됩니다 *이름*합니다. 와 함께 팝을 지정 하는 경우는 *식별자* 스택의 레코드에는 없는 **pop** 는 무시 됩니다.  
  
 *식별자*(선택 사항)  
 에 포함 될 수는 **푸시** 또는 **pop** 명령입니다. 경우 *식별자* 을 사용 하는 아니라면 **에** 또는 **오프** 지정자를 사용할 수도 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)