---
title: 경고 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- warning_CPP
- vc-pragma.warning
dev_langs:
- C++
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b739a3f72416b6ab58cbdba45a496e10fef4424
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="warning-pragma"></a>경고 Pragma
컴파일러 경고 메시지의 동작을 선택적으로 수정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
#pragma warning(   
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## <a name="remarks"></a>설명  
다음과 같은 경고 지정자 매개 변수를 사용할 수 있습니다.  
  
|경고 지정자|의미|  
|------------------------|-------------|  
|`1, 2, 3, 4`|주어진 수준을 지정된 경고에 적용합니다. 기본적으로 해제되어 있는 지정된 경고를 설정하기도 합니다.|  
|`default`|경고 동작을 기본값으로 다시 설정합니다. 기본적으로 해제되어 있는 지정된 경고를 설정하기도 합니다. 문서화된 기본 수준에서 경고가 생성됩니다.<br /><br /> 자세한 내용은 참조 [기본적으로 해제 되어 있는 컴파일러 경고](../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.|  
|`disable`|지정된 경고 메시지를 생성하지 마십시오.|  
|`error`|지정된 경고를 오류로 보고합니다.|  
|`once`|지정된 메시지를 한 번만 표시합니다.|  
|`suppress`|pragma의 현재 상태를 스택에 푸시하고 다음 줄에 지정된 경고를 비활성화한 후 pragma 상태가 다시 설정되도록 경고 스택을 표시합니다.|  
  
 다음 코드 문에서는 `warning-number-list` 매개 변수가 경고 번호를 여러 개 포함할 수 있으며 같은 pragma 지시문에 여러 `warning-specifier` 매개 변수를 지정할 수 있음을 보여 줍니다.  
  
```cpp  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 이 코드 문은 다음 코드와 기능적으로 동일합니다.  
  
```cpp  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 컴파일러가 0에서 999 사이의 경고 번호에 4000을 추가합니다.  
  
 4700-4999 범위에 속하고 코드 생성과 관련된 경고 번호의 경우 컴파일러가 함수의 왼쪽 중괄호를 발견할 때 적용되는 경고의 상태가 나머지 함수에 적용됩니다. 함수에 `warning` pragma를 사용하여 번호가 4699보다 큰 경고의 상태를 변경하면 함수가 끝난 후에야 변경 사항이 적용됩니다. 다음 예제에서는 코드 생성 경고 메시지를 사용하지 않도록 설정한 후 복원하기 위한 `warning` pragma의 올바른 배치를 보여 줍니다.  
  
```cpp  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 함수 본문 전체에서 `warning` pragma의 마지막 설정이 전체 함수에 적용됩니다.  
  
## <a name="push-and-pop"></a>푸시 및 팝  
 `warning` pragma에도 다음 구문을 지원 여기서 `n` 경고 수준 (1-4)을 나타냅니다.  
  
 `#pragma warning( push [ , n ] )`  
  
 `#pragma warning( pop )`  
   
 Pragma `warning( push )` 모든 경고에 대 한 현재 경고 상태를 저장 합니다. Pragma `warning( push, n )` 모든 경고에 대 한 현재 상태를 저장 하 고 글로벌 경고 수준을 설정 `n`합니다.  
  
 Pragma `warning( pop )` 스택에 밀어 넣은 마지막 경고 상태를 꺼냅니다. `push` 및 `pop` 간의 경고 상태 변경이 취소됩니다. 다음 예제를 고려해 보세요.  
  
```cpp  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 이 코드의 끝에서 `pop`은 4705, 4706, 4707을 포함하여 모든 경고 상태를 코드 시작 당시로 복원합니다.  
  
 헤더 파일을 작성할 때 `push` 및 `pop`을 사용하면 사용자가 경고 상태를 변경해도 헤더를 올바르게 컴파일할 수 있습니다. 헤더 시작 부분에서 `push`를 사용하고 끝 부분에서 `pop`을 사용합니다. 예를 들어, 경고 수준 4에서 완전히 컴파일되지 않는 헤더가 있을 경우 다음 코드를 사용하면 경고 수준이 3으로 변경되고 헤더 끝에서 원래의 경고 수준이 복원됩니다.  
  
```cpp  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 경고를 참조 하기 위해 표시 하지 않는 컴파일러에 대 한 자세한 내용은 [/FI](../build/reference/fi-name-forced-include-file.md) 및 [/w](../build/reference/compiler-option-warning-level.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)