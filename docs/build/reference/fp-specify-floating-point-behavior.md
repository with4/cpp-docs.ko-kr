---
title: -fp (부동 소수점 동작 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
dev_langs:
- C++
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af796b7143b3600130e9405782d618a5960d22fc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fp-specify-floating-point-behavior"></a>/fp(부동 소수점 동작 지정)
소스 코드 파일에서 부동 소수점 동작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/fp:[precise | except[-] | fast | strict ]  
```  
  
## <a name="flags"></a>플래그  
 **정확 하 게**  
 기본값입니다.  
  
 부동 소수점 계산의 정밀도를 변경할 수 있는 최적화를 비활성화하여 같음 및 같지 않음 연산에 대한 부동 소수점 테스트의 일관성이 향상됩니다. (엄격한 ANSI 준수를 위해 정해진 정밀도를 유지해야 합니다.) 기본적으로 x86 아키텍처 코드의 경우 컴파일러는 보조 프로세서의 80비트 레지스터를 사용하여 부동 소수점 계산의 중간 결과를 저장합니다. 따라서 프로그램 속도가 빨라지고 프로그램 크기가 작아집니다. 그러나 이 계산은 메모리에서 80비트 미만으로 표현되는 부동 소수점 데이터 형식을 처리하므로, 긴 계산을 통해 정밀도의 추가된 비트(80비트에서 작은 부동 소수점 형식의 비트 수 빼기)를 수반하는 경우에는 결과가 일치하지 않을 수도 있습니다.  
  
 와 **/fp: 정확한** x86 프로세서에서는 컴파일러가 반올림을 수행 형식의 변수에 `float` 할당 및 캐스트 매개 변수가 함수에 전달 되는 경우에 대 한 올바른 정밀도로 합니다. 이렇게 반올림하면 데이터가 해당 형식의 수용작업량보다 큰 상위값을 갖지 않도록 할 수 있습니다. 로 컴파일된 프로그램 **/fp: 정확한** 느리고 없이 컴파일 1 보다 큰 수 **/fp: 정확한**합니다. **/fp: 정확한** 내장 함수를 비활성화, 표준 런타임 라이브러리 루틴을 대신 사용 합니다. 자세한 내용은 [/Oi(내장 함수 만들기)](../../build/reference/oi-generate-intrinsic-functions.md)를 참조하세요.  
  
 다음과 같은 부동 소수점 동작이 활성화 됩니다 **/fp: 정확한**:  
  
-   축약, 즉 마지막에 한 번만 반올림하는 합성 연산을 사용하여 여러 개의 연산을 대체합니다.  
  
-   특별한 값(NaN, +infinity, -infinity, +0, -0)에 대해 유효하지 않은 식 최적화가 허용되지 않습니다. 최적화 x-x > 0 = x * 0 = x-0 > 0, = > x, x + 0 = > x, 및 0 x = >-x는 여러 가지 이유로에 유효 하지 않습니다. (IEEE 754 및 C99 표준을 참조하십시오.)  
  
-   컴파일러는 NaN이 관련된 비교를 올바르게 처리합니다. 예를 들어 x! = x 계산 **true** 경우 `x` 은 NaN 및 NaN이 관련 된 순서가 지정 된 비교에서 예외가 발생 합니다.  
  
-   식 평가는 C99 FLT_EVAL_METHOD=2를 따르지만 다음의 경우는 예외로 합니다. x86 프로세서를 프로그래밍할 때 FPU가 53비트의 정밀도로 설정되어 있기 때문에 long-double 정밀도로 간주됩니다.  
  
-   정확히 1.0을 곱하는 식은 다른 인수를 사용하도록 변형됩니다. x * y\*1.0 x로 변환 되므로\*y 합니다. 마찬가지로, x\*1.0\*y x로 변환 되므로\*y 합니다.  
  
-   정확히 1.0으로 나누는 식은 피제수를 사용하도록 변형됩니다. x * y/1.0 x로 변환 되므로\*y 합니다. 마찬가지로, x / 1.0\*y x로 변환 되므로\*y 합니다.  
  
 사용 하 여 **/fp: 정확한** 때 [fenv_access](../../preprocessor/fenv-access.md) 부동 소수점 식의 평가 컴파일 시간 등의 최적화를 해제 합니다. 켜져 있습니다. 예를 들어, 사용 하는 경우 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 부동 소수점 계산을 수행 하는 반올림 모드 및 컴파일러를 변경 하려면, 지정한 반올림 모드를 적용 하지 않은 경우가 아니면 `fenv_access`가 ON입니다.  
  
 **/fp: 정확한** 대체는 **/Op** 컴파일러 옵션입니다.  
  
 **빠른**  
 대부분의 경우 부동 소수점 연산을 최적화하기 위한 규칙을 완화하여 가장 빠른 코드를 만듭니다. 이렇게 하면 컴파일러에서 부동 소수점 코드를 속도에 맞게 최적화하는데, 그 대신 정확성이 저하됩니다. 때 **/fp: fast** 지정 된 컴파일러 수에서 올바르게 반올림할 대입문, 대입문 또는 함수 호출 및 중간 식의 반올림을 수행 하지 않을 수 있습니다. 컴파일러는 연산의 순서를 바꾸거나 연결 및 분배 규칙을 따르는 것과 같은 방식으로 유한 정밀도 결과에 대한 영향에 관계없이 대수 변형을 수행할 수 있습니다. 컴파일러는 C++ 형식 승격 규칙을 따르는 대신 연산 및 피연산자를 단정밀도로 변경할 수 있습니다. 부동 종점 관련 축약형 최적화는 항상 사용할 수 있습니다. ([fp_contract](../../preprocessor/fp-contract.md) on). 부동 소수점 예외 및 FPU 환경 액세스 비활성화 됩니다 (**/fp: 제외 하 고-** 인 것으로 간주 하 고 [fenv_access](../../preprocessor/fenv-access.md) 옵션이 OFF).  
  
 **/fp: fast** 함께 사용할 수 없습니다 **/fp: strict** 또는 **/fp: 정확한**합니다. 명령줄에 마지막으로 지정된 옵션이 사용됩니다. 둘 다 지정 하면 **/fp: fast** 및 **/fp: 제외한** 컴파일러 오류를 생성 합니다.  
  
 지정 [/Za, /Ze (언어 확장명 사용 안 함)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI 호환성) 및 **/fp: fast** 예기치 않은 동작이 발생할 수 있습니다. 예를 들어, 단정밀도 부동 소수점 연산이 단정밀도로 반올림되지 않을 수 있습니다.  
  
 **except [-]**  
 신뢰할 수 있는 부동 소수점 예외 모델입니다. 예외가 트리거되는 즉시 발생합니다. 이 옵션은 기본적으로 해제되어 있습니다. 옵션에 빼기 기호를 추가하면 옵션이 명시적으로 해제됩니다.  
  
 **엄격한**  
 가장 엄격한 부동 소수점 모델입니다. **/fp: strict** 하면 [fp_contract](../../preprocessor/fp-contract.md) 는 OFF 및 [fenv_access](../../preprocessor/fenv-access.md) 가 ON입니다. **/fp: 제외한** 인 것으로 간주 하 고 명시적으로 지정 하 여 해제할 수 있습니다 **/fp: 제외 하 고-** 합니다. 와 함께 사용할 경우 **/fp: 제외 하 고-**, **/fp: strict** 부동 소수점 의미 체계를 엄격 하 게 확인 예외 이벤트를 고려 하지 않고 있습니다.  
  
## <a name="remarks"></a>설명  
 여러 **/fp** 동일한 컴파일에서 옵션을 지정할 수 있습니다.  
  
 함수에 의해 부동 소수점 동작을 제어 하려면 참조는 [float_control](../../preprocessor/float-control.md) pragma입니다. 이 재정의 **/fp** 컴파일러 설정을 사용 합니다. 로컬 부동 소수점 동작을 저장 및 복원하는 것이 엔지니어링 방법으로 좋습니다.  
  
```cpp  
#pragma float_control(precise, on, push)  
// Code that uses /fp:precise mode  
#pragma float_control(pop)  
```  
  
 대부분의 부동 소수점 최적화와 관련 된 **/fp: strict**, **/fp: 제외 하 고** (및 해당 해당 pragma) 및 `fp_contract` pragma는 컴퓨터에 따라 다릅니다. **/fp: strict** 및 **/fp: 제외 하 고** 와 호환 되지 않는 **/clr**합니다.  
  
 **/fp: 정확한** 응용 프로그램의 부동 소수점 요구 사항 대부분을 해결 해야 합니다. 사용할 수 있습니다 **/fp: 제외한** 및 **/fp: strict**, 되지만 성능이 약간 저하 될 수 있습니다. 성능이 가장 중요 한 경우 사용할 수도 **/fp: fast**합니다.  
  
 **/fp: strict**, **/fp: fast**, 및 **/fp: 정확한** 정밀도 (정확도) 모드입니다. 이러한 옵션은 한 번에 하나만 적용할 수 있습니다. 두 **/fp: strict** 및 **/fp: 정확한** 컴파일러 마지막에 처리를 사용 하 여 지정 됩니다. 둘 다 **/fp: strict** 및 **/fp: fast** 지정할 수 없습니다.  
  
 자세한 내용은 참조 [Microsoft Visual c + + 부동 소수점 최적화](http://msdn.microsoft.com/library/aa289157.aspx)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **C/c + +** 노드.  
  
4.  선택 된 **코드 생성** 속성 페이지.  
  
5.  수정 된 **부동 소수점 모델** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [Microsoft Visual c + + 지점 최적화 부동](http://msdn.microsoft.com/library/aa289157.aspx)