---
title: '#define 지시문 (C/c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#define'
dev_langs:
- C++
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8875c2b2c744a16f936fd2220826f23413a0e6c9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846157"
---
# <a name="define-directive-cc"></a>#define 지시문 (C/C++)
`#define` 만듭니다는 *매크로*, 식별자 또는 매개 변수화 된 식별자와 토큰 문자열 연결 하는입니다. 매크로가 정의된 후 컴파일러는 소스 파일에서 발생하는 각 식별자를 토큰 문자열로 대체할 수 있습니다.  
  
## <a name="syntax"></a>구문  
 `#define` *식별자* *토큰 문자열*선택  
  
 `#define` *식별자* `(` *식별자*opt`,`*...*  `,` *식별자*opt`)`*토큰 문자열*선택  
  
## <a name="remarks"></a>설명  
 `#define` 지시문을 대체할 컴파일러가 *토큰 문자열* 의 각 항목에 대 한 *식별자* 소스 파일에 있습니다. *식별자* 토큰을 형성 하는 경우에 대체 됩니다. 즉, *식별자* 문자열에서 또는 긴 식별자의 일부로 설명에 표시 되는 경우 대체 되지 않습니다. 자세한 내용은 참조 [토큰](../cpp/tokens-cpp.md)합니다.  
  
 *토큰 문자열* 인수 일련의 키워드, 상수 또는 전체 문을 같은 토큰 구성 됩니다. 하나 이상의 공백 문자를 구분 해야 *토큰 문자열* 에서 *식별자*합니다. 이 공백은 대체 텍스트의 일부 또는 대체 텍스트의 최종 토큰 뒤에 오는 공백으로 간주되지 않습니다.  
  
 A `#define` 없이 *토큰 문자열* 의 항목을 제거 *식별자* 원본 파일에서 합니다. *식별자* 정의 되어 있고 사용 하 여 테스트할 수 있습니다는 `#if defined` 및 `#ifdef` 지시문입니다.  
  
 두 번째 구문 형식에서는 매개 변수를 사용하여 함수 형식 매크로를 정의합니다. 이 형식은 괄호 안에 표시되어야 하는 매개 변수의 선택 목록을 허용합니다. 매크로의 정의 되 고 각 후속 발생 된 후 *식별자*( *식별자*opt,..., *식별자*opt)의 버전으로 대체는  *토큰 문자열* 실제 인수가 정식 매개 변수 대신 인수입니다.  
  
 에 표시 된 형식 매개 변수 이름을 *토큰 문자열* 실제 값의 대체 위치를 표시 합니다. 각 매개 변수 이름에 여러 번 나타날 수 *토큰 문자열*, 이름은 순서에 관계 없이에 나타날 수 있습니다. 호출의 인수 개수는 매크로 정의의 매개 변수 개수와 일치해야 합니다. 괄호를 자유롭게 사용하여 복잡한 실제 인수가 올바르게 해석되도록 합니다.  
  
 목록의 형식 매개 변수는 쉼표로 구분됩니다. 목록의 각 이름은 고유해야 하고 목록은 괄호로 묶여야 합니다. 공백 없이 구분할 수 *식별자* 및 여는 괄호입니다. 줄 연결을 사용 하 여-백슬래시를 배치 (`\`)는 줄 바꿈 문자 바로 앞-여러 소스 줄에 긴 지시문에 대 한 합니다. 형식 매개 변수 이름의 범위 종료 하는 새 줄으로 확장 *토큰 문자열*합니다.  
  
 매크로가 두 번째 구문 형식으로 정의된 경우, 인수 목록이 그 뒤에 오는 텍스트 인스턴스는 매크로 호출을 나타냅니다. 인스턴스 뒤에 실제 인수가 *식별자* 소스 파일에는 매크로 정의의 해당 형식 매개 변수와 일치 합니다. 각 형식 매개 변수에서 *토큰 문자열* 하는 앞에 문자열 화 (`#`), charizing (`#@`), 또는 토큰 붙여넣기 (`##`) 연산자를 붙는 형태 또는 `##` 연산자는 해당 실제 인수로 바뀝니다. 실제 인수의 모든 매크로는 지시문이 형식 매개 변수를 대체하기 전에 확장됩니다. (연산자에 설명 된 [전처리기 연산자](../preprocessor/preprocessor-operators.md).)  
  
 인수를 가진 매크로에 대한 다음 예제는 `#define` 구문의 두 번째 형식을 설명합니다.  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 파생 효과가 있는 인수를 사용하면 매크로가 예기치 않은 결과를 생성하기도 합니다. 지정 된 형식 매개 변수에서 여러 번 나타날 수 *토큰 문자열*합니다. 해당 형식 매개 변수가 파생 효과가 있는 식으로 대체되는 경우 해당 식은 그 파생 효과로 인해 두 번 이상 계산됩니다. (아래의 예제를 참조 하십시오. [토큰 붙여넣기 연산자 (#)](../preprocessor/token-pasting-operator-hash-hash.md).)  
  
 `#undef` 지시문으로 인해 식별자의 전처리기 정의가 무시될 수 있습니다. 참조 [지시문 #undef](../preprocessor/hash-undef-directive-c-cpp.md) 자세한 정보에 대 한 합니다.  
  
 정의 하 고 매크로의 이름이 발생 하는 경우 *토큰 문자열* (도 다른 매크로 확장)의 결과 축소 합니다.  
  
 같은 이름을 가진 매크로에 대한 두 번째 `#define`은 두 번째 토큰 시퀀스가 첫 번째와 동일하지 않으면 경고를 생성합니다.  
  
 **Microsoft 전용**  
  
 Microsoft C/C++에서는 새 정의가 원래 정의와 구문적으로 동일할 경우 매크로를 재정의할 수 있습니다. 즉, 두 개의 정의에서 매개 변수 이름은 각기 다를 수 있습니다. 이 동작은 두 정의의 어휘가 동일해야 하는 [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C와는 다릅니다.  
  
 예를 들어, 다음 두 매크로는 매개 변수 이름만 제외하면 모두 동일합니다. [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C는 재정의 허용 하지 않습니다 되지만 Microsoft C/c + +는 오류 없이 컴파일합니다.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 한편 다음 동일하지 않은 두 매크로는 Microsoft C/C++에서 경고를 생성합니다.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **Microsoft 전용 종료**  
  
 이 예제에서는 `#define` 지시문을 설명합니다.  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 첫 번째 명령문은 `WIDTH` 식별자를 정수 상수 80으로 정의하고, `LENGTH`를 `WIDTH` 더하기 정수 상수 10으로 정의합니다. `LENGTH`가 나타날 때마다 (`WIDTH + 10`)으로 바뀝니다. 또한, `WIDTH + 10`이 발생할 때마다 (`80 + 10`) 식으로 바뀝니다. `WIDTH + 10`을 묶는 괄호는 다음과 같은 문에서 해석을 제어하기 때문에 중요합니다.  
  
```  
var = LENGTH * 20;  
```  
  
 전처리 단계 후 문은 다음과 같아집니다.  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 결과 값이 1800으로 계산됩니다. 괄호가 없을 경우 결과는 다음과 같습니다.  
  
```  
var = 80 + 10 * 20;  
```  
  
 이 경우 280을 계산합니다.  
  
 **Microsoft 전용**  
  
 매크로 및 상수를 정의 고 [/D](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션은 사용 하는 것과 같습니다는 `#define` 전처리 지시문 파일의 시작 부분에 있습니다. /D 옵션을 사용하여 최대 30 매크로로 정의할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)