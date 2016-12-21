---
title: "/fp(부동 소수점 동작 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.floatingPointModel"
  - "VC.Project.VCCLWCECompilerTool.FloatingPointExceptions"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.floatingPointModel"
  - "VC.Project.VCCLCompilerTool.FloatingPointExceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/fp 컴파일러 옵션[C++]"
  - "-fp 컴파일러 옵션[C++]"
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /fp(부동 소수점 동작 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

소스 코드 파일에서 부동 소수점 동작을 지정합니다.  
  
## 구문  
  
```  
/fp:[precise | except[-] | fast | strict ]  
```  
  
## Flags  
 **precise**  
 기본값입니다.  
  
 부동 소수점 계산의 정밀도를 변경할 수 있는 최적화를 비활성화하여 같음 및 같지 않음 연산에 대한 부동 소수점 테스트의 일관성이 향상됩니다. \(엄격한 ANSI 준수를 위해 정해진 정밀도를 유지해야 합니다.\) 기본적으로 x86 아키텍처 코드의 경우 컴파일러는 보조 프로세서의 80비트 레지스터를 사용하여 부동 소수점 계산의 중간 결과를 저장합니다.  따라서 프로그램 속도가 빨라지고 프로그램 크기가 작아집니다.  그러나 이 계산은 메모리에서 80비트 미만으로 표현되는 부동 소수점 데이터 형식을 처리하므로, 긴 계산을 통해 정밀도의 추가된 비트\(80비트에서 작은 부동 소수점 형식의 비트 수 빼기\)를 수반하는 경우에는 결과가 일치하지 않을 수도 있습니다.  
  
 x86 프로세서에 **\/fp:precise**를 사용하면 함수에 매개 변수를 전달할 때 `float` 형식의 변수에 대해 컴파일러가 할당 및 캐스트에 올바른 정밀도로 반올림을 수행합니다.  이렇게 반올림하면 데이터가 해당 형식의 수용작업량보다 큰 상위값을 갖지 않도록 할 수 있습니다.  **\/fp:precise**를 사용하여 컴파일한 프로그램은 **\/fp:precise**를 사용하지 않고 컴파일한 프로그램보다 속도가 느리고 크기가 더 클 수 있습니다.  **\/fp:precise**는 내장 함수를 비활성화하고 표준 런타임 라이브러리 루틴을 대신 사용합니다.  자세한 내용은 [\/Oi\(내장 함수 만들기\)](../../build/reference/oi-generate-intrinsic-functions.md)을 참조하십시오.  
  
 **\/fp:precise**를 사용하면 다음과 같은 부동 소수점 동작이 활성화됩니다.  
  
-   축약, 즉 마지막에 한 번만 반올림하는 합성 연산을 사용하여 여러 개의 연산을 대체합니다.  
  
-   특별한 값\(NaN, \+infinity, \-infinity, \+0, \-0\)에 대해 유효하지 않은 식 최적화가 허용되지 않습니다.  최적화 x\-x \=\> 0, x\*0 \=\> 0, x\-0 \=\> x, x\+0 \=\> x 및 0\-x \=\> \-x가 올바르지 않은 이유는 여러 가지가 있습니다. \(IEEE 754 및 C99 표준을 참조하십시오.\)  
  
-   컴파일러는 NaN이 관련된 비교를 올바르게 처리합니다.  예를 들어, `x`가 NaN이고 NaN이 관련된 순서 지정 비교에서 예외가 발생하는 경우 x \!\= x는 **true**입니다.  
  
-   식 평가는 C99 FLT\_EVAL\_METHOD\=2를 따르지만 다음의 경우는 예외로 합니다. x86 프로세서를 프로그래밍할 때 FPU가 53비트의 정밀도로 설정되어 있기 때문에 long\-double 정밀도로 간주됩니다.  
  
-   정확히 1.0을 곱하는 식은 다른 인수를 사용하도록 변환됩니다.  x\*y\*1.0은 x\*y로 변환됩니다.  마찬가지로, x\*1.0\*y도 x\*y로 변환됩니다.  
  
-   정확히 1.0으로 나누는 식은 피제수를 사용하도록 변환됩니다.  x\*y\/1.0은 x\*y로 변환됩니다.  마찬가지로, x\/1.0\*y도 x\*y로 변환됩니다.  
  
 [fenv\_access](../../preprocessor/fenv-access.md)를 ON으로 설정하고 **\/fp:precise**를 사용하면 부동 소수점 식의 컴파일 타임 계산과 같은 최적화를 사용하지 않습니다.  예를 들어, [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)를 사용하여 반올림 모드를 변경하면 컴파일러에서 부동 소수점 계산을 수행할 때 사용자가 지정한 반올림 모드가 적용되지 않습니다. 이 반올림 모드를 적용하려면 `fenv_access`를 ON으로 설정해야 합니다.  
  
 **\/fp:precise**는 **\/Op** 컴파일러 옵션을 대체합니다.  
  
 **fast**  
 대부분의 경우 부동 소수점 연산을 최적화하기 위한 규칙을 완화하여 가장 빠른 코드를 만듭니다.  이렇게 하면 컴파일러에서 부동 소수점 코드를 속도에 맞게 최적화하는데, 그 대신 정확성이 저하됩니다.  **\/fp:fast**가 지정되면 컴파일러는 대입문, 형식 캐스팅 또는 함수 호출에서 올바르게 반올림할 수 없고 중간 식의 반올림을 수행할 수 없습니다.  컴파일러는 연산의 순서를 바꾸거나 연결 및 분배 규칙을 따르는 것과 같은 방식으로 유한 정밀도 결과에 대한 영향에 관계없이 대수 변환을 수행할 수 있습니다.  컴파일러는 C\+\+ 형식 승격 규칙을 따르는 대신 연산 및 피연산자를 단정밀도로 변경할 수 있습니다.  부동 소수점별 축약 최적화는 항상 사용합니다\([fp\_contract](../../preprocessor/fp-contract.md)는 ON으로 설정됨\).  부동 소수점 예외 및 FPU 환경 액세스를 사용할 수 없습니다\(**\/fp:except\-**는 암시적이고 [fenv\_access](../../preprocessor/fenv-access.md)는 OFF로 설정됨\).  
  
 **\/fp:fast**는 **\/fp:strict** 또는 **\/fp:precise**와 함께 사용할 수 없습니다.  명령줄에 마지막으로 지정된 옵션이 사용됩니다.  **\/fp:fast** 및 **\/fp:except**를 둘 다 지정하면 컴파일러 오류가 발생합니다.  
  
 [\/Za, \/Ze\(언어 확장 사용 안 함\)](../../build/reference/za-ze-disable-language-extensions.md)\(ANSI 호환성\) 및 **\/fp:fast**를 지정하면 예기치 않은 동작이 일어날 수 있습니다.  예를 들어, 단정밀도 부동 소수점 연산이 단정밀도로 반올림되지 않을 수 있습니다.  
  
 **except\[\-\]**  
 신뢰할 수 있는 부동 소수점 예외 모델입니다.  예외가 트리거되는 즉시 발생합니다.  이 옵션은 기본적으로 해제되어 있습니다.  옵션에 빼기 기호를 추가하면 옵션이 명시적으로 해제됩니다.  
  
 **strict**  
 가장 엄격한 부동 소수점 모델입니다.  **\/fp:strict**를 사용하면 [fp\_contract](../../preprocessor/fp-contract.md)가 OFF로 설정되고 [fenv\_access](../../preprocessor/fenv-access.md)가 ON으로 설정됩니다.  **\/fp:except**는 암시적이며 **\/fp:except\-**를 지정하여 명시적으로 비활성화할 수 있습니다.  **\/fp:except\-**와 함께 **\/fp:strict**를 사용하면 예외 이벤트를 고려하지 않은 채 엄격한 부동 소수점 의미 체계가 적용됩니다.  
  
## 설명  
 여러 **\/fp** 옵션을 동일한 컴파일에서 지정할 수 있습니다.  
  
 함수별로 부동 소수점 동작을 제어하는 방법은 [float\_control](../../preprocessor/float-control.md) pragma를 참조하십시오.  이로 인해 **\/fp** 컴파일러 설정이 재정의됩니다.  로컬 부동 소수점 동작을 저장 및 복원하는 것이 엔지니어링 방법으로 좋습니다.  
  
```css  
#pragma float_control(precise, on, push)  
// Code that uses /fp:precise mode  
#pragma float_control(pop)  
```  
  
 **\/fp:strict**, **\/fp:except** 및 상응하는 pragma, `fp_contract` pragma와 관련된 대부분의 부동 소수점 최적화 동작은 컴퓨터에 따라 달라집니다.  **\/fp:strict** 및 **\/fp:except**는 **\/clr**과 함께 사용할 수 없습니다.  
  
 **\/fp:precise**로 응용 프로그램의 부동 소수점 요구 사항 대부분을 처리할 수 있습니다.  **\/fp:except**와 **\/fp:strict**를 사용할 수 있지만 이 경우 성능이 약간 저하될 수 있습니다.  성능이 더 중요한 경우 **\/fp:fast**를 사용할지 고려합니다.  
  
 **\/fp:strict**, **\/fp:fast** 및 **\/fp:precise**는 정밀도\(정확도\) 모드입니다.  이러한 옵션은 한 번에 하나만 적용할 수 있습니다.  **\/fp:strict**와 **\/fp:precise**를 둘 다 지정하면 컴파일러는 마지막에 처리한 옵션을 사용합니다.  **\/fp:strict**와 **\/fp:fast** 모두 지정할 수는 없습니다.  
  
 자세한 내용은 [Microsoft Visual C\+\+ 부동 소수점 최적화](http://msdn.microsoft.com/library/aa289157.aspx)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **C\/C\+\+** 노드를 확장합니다.  
  
4.  **코드 생성** 속성 페이지를 선택합니다.  
  
5.  **부동 소수점 모델** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [Microsoft Visual C\+\+ 부동 소수점 최적화](http://msdn.microsoft.com/library/aa289157.aspx)