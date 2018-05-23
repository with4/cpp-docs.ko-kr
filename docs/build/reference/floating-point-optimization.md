---
title: Microsoft Visual c + + 부동 소수점 최적화 | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35c9263fa6252469124eefb0dfd575ef5bd2ac34
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2018
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual c + + 부동 소수점 최적화

부동 소수점 의미 체계를 관리 하는 Microsoft c + + 컴파일러의 방법을 사용 하 여 부동 소수점 코드를 최적화에 대 한 핸들을 가져옵니다. 부동 소수점 코드에만 안전 최적화가 수행 되었는지 확인 하는 동안 빠른 프로그램을 만듭니다.

## <a name="optimization-of-floating-point-code-in-c"></a>C + +에서 부동 소수점 코드가 최적화

C + + 컴파일러 최적화 기계어 코드에 소스 코드를 변환 뿐만 아니라,의 효율성을 개선 및/또는 크기를 줄일 수 있는 방법으로 컴퓨터 지침을 정렬 합니다. 그러나 여러 가지 일반적인 최적화가 부동 소수점 계산에 적용 될 때 반드시 안전 하지 않습니다. David 길동, "작업의 모든 컴퓨터 과학자 해야 알고에 대 한 부동 소수점 산술"에서 가져온 다음 합계 알고리즘 표시 될 수 있습니다 이러한 좋은 예 *컴퓨팅 설문 조사*, 1991 년 3 월, pg 합니다. 203:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

이 함수는 n 추가 **float** 배열 벡터에 있는 값 `A`합니다. 루프 본문 내에서 알고리즘 합계의 다음 단계에 적용 되는 "수정" 값을 계산 합니다. 이 메서드는 o (n) 시간 복잡도 유지 하면서 단순 합계를 비교 하 여 누적 반올림 오류 상당히 감소 됩니다.

Naïve c + + 컴파일러는 부동 소수점 연산 실수 산술와 동일한 대 수 규칙을 따르는지를 생각할 수 있습니다. 이러한 컴파일러 다음 잘못 끝납니다입니다.

> C T-합-Y = = = > (sum + Y)-합계-Y = = > 0;

즉, C의 알려진된 값은 항상 상수 0입니다. 그런 다음 후속 식에이 상수 값이 전파 됩니다, 단순 합계를 루프 본문이 줄어듭니다. 정확 하 게,

> Y = [i]-C = = > Y = [i]<br/>T = 합계 + Y = = > T = 합계 + [i]<br/>합계 = T = = > 합계 = 합계 + [i]

논리 변환 naïve 컴파일러에 따라서는 `KahanSum` 함수 됩니다:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

변환 된 알고리즘은 속도가 더 있지만 *프로그래머의 의도 정확 하 게 표현은 전혀*합니다. 신중 하 게 만든된 오류 수정을 완전히 제거 하 고 모든 관련 오류로 간단 하 고 직접 합계 알고리즘으로 남아 있는 하는 키를 누릅니다.

물론 정교한 c + + 컴파일러는이 형식은 알고 규칙 실시간의 산술 적용 되지 않습니다 일반적으로 부동 소수점 연산입니다. 그러나 복잡 한 c + + 컴파일러 계속 해 서 올바르게 해석 되지 않을 수도 프로그래머의 의도 합니다.

가능한 "(호출된의 레지스터 등록 값) 레지스터에 많은 값을 포함 하는 최적화를 많이 것이 좋습니다. 에 `KahanSum` 예제에서는이 최적화 하려고 기초한 변수 `C`, `Y` 및 `T` 루프 본문 내 에서만 사용 되기 때문입니다. 레지스터 정밀도 52bits 23bits (단일) 대신 (double) 이면이 최적화 효과적으로 형식 승격 `C`, `Y` 및 `T` 입력 **double**합니다. Sum 변수도 레지스터 마찬가지로 하는 경우에 단 정밀도의 인코딩된 유지 됩니다. 이 변환의 의미 체계 `KahanSum` 다음과

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

하지만 `Y`, `T` 및 `C` 이제 계산 높은 정밀도에서 값에 따라 덜 정확한 결과 생성할 수 있습니다이 새 인코딩을 `A[]`합니다. 따라서 겉보기도 무해 최적화 가질 수 있으며 부정적인 결과가 발생 합니다.

이러한 종류의 최적화 문제 "까다로운" 부동 소수점 코드를 제한 하지 않습니다. 부동 소수점도 간단한 알고리즘 올바르게 최적화 때 실패할 수 있습니다. 간단 하 고 직접 합계 알고리즘을 고려해 야 합니다.

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

이기 때문에 일부 부동 소수점 단위가 동시에 여러 작업을 수행할 수 있으므로 컴파일러는 스칼라 감소가 최적화를 수행할 수도 있습니다. 이 최적화는 효과적으로 다음으로 위쪽에서 간단한 Sum 함수를 변환:

```cpp
float Sum( const float A[], int n )
{
   int n4 = n-n%4; // or n4=n4&(~3)
   int i;
   float sum=0, sum1=0, sum2=0, sum3=0;
   for (i=0; i<n4; i+=4)
   {
      sum = sum + A[i];
      sum1 = sum1 + A[i+1];
      sum2 = sum2 + A[i+2];
      sum3 = sum3 + A[i+3];
   }
   sum = sum + sum1 + sum2 + sum3;
   for (; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

함수는 이제 각 단계에서 동시에 처리할 수 있는 네 개의 별도 합계를 유지 합니다. 최적화 된 함수는 이제 훨씬, 있지만 최적화 된 결과 최적화 되지 않은 결과와에서 크게 다르게 수 있습니다. 이 변경 하는 경우 컴파일러는 결합형 부동 소수점 더하기; 가정 즉, 이러한 두 표현식은 동일: `(a + b) + c == a + (b + c)`합니다. 그러나 연관성 항상 true 유지 하지 않으면 부동 소수점 숫자입니다. 대신으로 합계 계산:

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

변환 된 함수에는 이제으로 결과 계산

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

일부 값에 대 한 `A[]`, 추가 작업의 다른 순서이 예기치 않은 결과가 발생할 수 있습니다. 더욱 복잡 해질, 일부 프로그래머 같은 최적화를 예측 하 고 적절 하 게을 보정 하도록 선택 될 수 있습니다. 이 경우 프로그램 배열을 생성할 수 `A` 다른 순서에 따라 최적화 된 합계에 예상 결과 되도록 합니다. 또한 대부분의 경우에 최적화 된 결과의 정확도 "가까이 있어" 수 있습니다. 최적화 강력한 속도 이점을 제공 하는 경우 특히 유용 합니다. 비디오 게임, 예를 들어 필요 가능한 속도 훨씬 있지만 매우 정확 하 게 부동 소수점 계산을 자주 필요 하지 않습니다. 컴파일러 결정권자 속도 정확도의 종종 서로 다른 목표를 제어 하는 프로그래머를 위한 메커니즘을 제공 하므로 해야 합니다.

일부 컴파일러 최적화의 각 유형에 대해 별도 스위치를 제공 하 여 속도 정확도 간의 균형을 해결 합니다. 따라서 개발자가 부동 소수점 정확도 특정 응용 프로그램에 대 한 변경 내용이 발생 하는 최적화를 사용 하지 않도록 설정할 수 있습니다. 이 솔루션은 높은 수준의 컴파일러에 대 한 제어 제공할 수 있습니다, 하는 동안에 몇 가지 추가 문제가 도입 되었습니다.

- 것 명확 하지 않습니다 종종 설정 또는 해제 전환입니다.
- 모든 단일 최적화를 해제 하면 비 부동 소수점 코드의 성능을 저하 될 수 있습니다.
- 각 추가 스위치 많은 새 스위치 조합이;를 발생 시킵니다. 조합의 수는 신속 하 게 반환 됩니다.

따라서 각 최적화에 대 한 별도 스위치를 제공 하는 매력적인 보일 수 있지만, 이러한 컴파일러 사용할 복잡 하 고 신뢰할 수 없는 합니다.

많은 c + + 컴파일러는 제공 된 *일관성* 부동 소수점 모델 (통해는 **/Op** 또는 **/fltconsistency** 전환) 개발자 규격 프로그램을 만들 수 있습니다 엄격한 부동 소수점 의미 체계를 사용 참여 하 고,이 모델에서 부동 소수점 계산에서 대부분의 최적화를 사용 하 여 부동 소수점 코드에 대 한 이러한 최적화를 허용 하는 동안 컴파일러를 방지 합니다. 그러나 일관성 모델에는 어두운 측. 다른 FPU 아키텍처, 거의 모든 구현에서 예측 가능한 결과 반환 하기 위해 **/Op** 사용자에 게 라운드 중간 식 전체 자릿수 지정 되었습니다; 예를 들어 다음 식을 참조 하십시오.

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

일관 되 고 반복 가능한 결과 생성 하기 위해 **/Op**, 다음과 같이 구현 된 경우 처럼이 식을 평가 합니다.

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

최종 결과 단 정밀도 반올림 오류에서 이제 저하 *식을 계산의 각 단계에서*합니다. 이 해석을 모든 c + + 의미 체계 규칙을 엄격 하 게 중단 하지 않습니다, 되지만 될 부동 소수점 식을 평가 하는 가장 좋은 방법은 거의 없습니다. 일반적으로 중간 높은 정밀도 효과적이 지는 대로 결과 계산 하 좋을 것입니다. 예를 들어, 좋을 식을 계산 하지 `a = b * c + d * e` 에서 같이 더 높은 정밀도에서

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

더 좋은 방법은 또는

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

을 더 높은 정밀도에서 중간 결과 계산할 때 최종 결과 매우 부정확 합니다. 하지만, 일관성 모델을 사용 하 여 정확 하 게 사용자가 안전 하지 않은 최적화를 비활성화 하 여 오류를 줄일 하려고 할 때 오류가 발생할 가능성이 향상 됩니다. 따라서 일관성 모델의 정확도 높이기 다 동시에 제공 하면서 효율성을 줄일 심각 하 게 수 있습니다. 심각한 숫자 프로그래머에 게 매우 우수한 상쇄 처럼 못하는이 하며 모델은 일반적으로 받지 못했음이 주된 이유입니다.

부터 버전 8.0 (C++® 2005), Microsoft c + + 컴파일러 보다 더 효율적을 제공 합니다. 프로그래머가 세 가지 일반 부동 소수점 모드 중 하나를 선택할 수: fp: precise,: fast 및 fp: 엄격 하 게 합니다.

- Fp 아래: precise만 안전 최적화가 수행 부동 소수점 코드를 달리 **/Op**, 중간 계산은 실제 가장 높은 정밀도에서 지속적으로 수행 됩니다.
- : fast 모드는 저하 보다 적극적으로 최적화에 대 한 허용 되는 부동 소수점 규칙을 완화 합니다.
- fp: strict 모드에서는 fp 모든 일반 올바른지: fp 예외 의미 체계를 사용 하도록 설정 하 고 FPU 환경 변경 (예: 반올림 방향을 등 레지스터 정밀도로 변경) 있는 경우 잘못 된 변환을 방지 하는 동안 정확 하 게 합니다.

명령줄 스위치 또는 컴파일러 pragma; 여 부동 소수점 예외 의미 체계를 독립적으로 제어할 수 있습니다. 기본적으로 부동 소수점 예외 의미 체계가 fp에서 비활성화: 정확 하 게 사용 가능 하 고 fp 아래: 엄격 하 게 합니다. 컴파일러는 또한 FPU 환경 민감도 축약 등의 특정 부동 소수점 최적화 동작은 특정에 대 한 제어를 제공합니다. 이 간단 모델에서는 개발자가 다양 한 너무 많은 컴파일러 스위치의 부담 하거나 잠재 원하지 않는 부작용의 하지 않고 부동 소수점 코드의 컴파일 제어 합니다.

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Fp: 부동 소수점 의미 체계에 대 한 정확한 모드

기본 부동 소수점 의미 체계가 모드는 fp: 정확 하 게 합니다. 이 모드를 선택 하는 경우 컴파일러가 부동 소수점 연산을 최적화 하는 경우 보안 규칙 집합을를 엄격 하 게 준수 합니다. 이러한 규칙에는 부동 소수점 계산의 정확성을 유지 하면서 효율적인 기계어 코드를 생성 하도록 컴파일러에 허용 합니다. Fast 프로덕션을 용이 하 게 하려면 프로그램을 fp: 정확한 모델 (있습니다 설정할 수도 있지만 명시적으로) 부동 소수점 예외 의미 체계가 사용 하지 않도록 설정 합니다. Microsoft가 fp 선택한: 빠르고 정확한 프로그램을 만들기 때문에 기본 부동 소수점 모드로 정확 합니다.

Fp를 명시적으로 요청할: 명령줄 컴파일러를 사용 하 여를 사용 하 여 정확한 모드는 [/fp: 정확한](fp-specify-floating-point-behavior.md) 전환:

> cl /fp: 정확한 source.cpp

이렇게 하면 fp를 사용 하도록 컴파일러에: source.cpp 파일에 대 한 코드를 생성할 때의 정확한 의미 합니다. Fp: 정확한 모델 사용 하 여 함수에서 함수 별로 호출 될 수도 있습니다는 [float_control 컴파일러 pragma](#the-float-control-pragma)합니다.

Fp 아래: precise 모드 컴파일러가 부동 소수점 계산의 정확도 방해할 수 있는 모든 최적화 되지 수행 합니다. 컴파일러가 할당에서 올바르게 반올림할 항상 됩니다, 포인터로 변환 및 함수 호출, 고 중간 반올림 지속적으로 수행 됩니다 같은 정밀도에 FPU 레지스터입니다. 축약 등의 안전 최적화는 기본적으로 활성화 됩니다. 예외 의미 체계가 및 FPU 환경 민감도 기본적으로 비활성화 됩니다.

|fp: 정확한 의미|설명|
|-|-|
|의미 체계를 반올림합니다.|대입문 할당에 명시적으로 반올림 하 고 함수 호출 합니다. 중간 식 레지스터 정밀도에 평가 됩니다.|
|대 수 변형|엄격한 준수를 관련이, 분배 비 부동 소수점 대 수 변형을에 항상 보장 되지 않는 동일한 결과 생성 합니다.|
|축약|기본적으로 사용할 수 있습니다. 자세한 내용은 섹션을 참조 하십시오. [fp_contract pragma](#the-fp-contract-pragma)합니다.|
|부동 소수점 계산 순서|컴파일러는 최종 결과 변경 되지 않습니다 부동 소수점 식의 평가 순서를 변경할 수 있습니다.|
|FPU 환경 액세스|기본적으로 사용 하지 않습니다. 자세한 내용은 섹션을 참조 하십시오. [fenv_access pragma](#the-fenv-access-pragma)합니다. 기본 전체 자릿수와 반올림 모드 가정 합니다.|
|부동 소수점 예외 의미 체계|기본적으로 사용 하지 않습니다. 자세한 내용은 참조 [/fp: 제외한](fp-specify-floating-point-behavior.md)합니다.|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Fp에서 부동 소수점 식에 대 한 의미를 반올림: 정확 하 게

Fp: 정확한 모델은 항상 식 계산에서의 특정 지점에만 명시적으로 반올림 하는 가장 높은 실용적인 정밀도에서 중간 계산을 수행 합니다. 네 곳에서 항상 사용자 지정 된 정밀도로 반올림이 수행: (a) 배정을, (b) 변환 수행 될 때, (c) 때 부동 소수점 값을 전달 됩니다 인수로 서 함수와에서 부동 소수점 값이 반환 됩니다 (d) 경우에 함수입니다. 중간 결과의 정확도 플랫폼 종속 중간 계산 레지스터 정밀도에서 항상 수행 되므로, (경우에 전체 자릿수를 지정 된 사용자로 정확한은 항상 전체 자릿수)입니다.

다음 코드에 대입 식을 것이 좋습니다. '=' 할당 연산자의 오른쪽에 식이 레지스터 정밀도에 계산 되며 할당의 왼쪽의 형식으로 명시적으로 반올림 합니다.

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

로 계산 됩니다.

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

중간 결과 명시적으로 반올림, 변환 단계를 소개 합니다. 예를 들어 이전 코드를 추가 하 여 수정 하는 경우 명시적 형식 캐스팅, 중간 식 (c * d)는 변환의 형식으로 반올림 됩니다.

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

로 계산 됩니다.

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

이 반올림 방법의 하나 구현은 일부 겉보기에 해당 하는 변환 실제로 있는 없는다는 동일한 의미 체계입니다. 예를 들어, 다음 변환에는 두 할당 식으로 단일 할당 식을 분할합니다.

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

가 같음

```cpp
float a, b, c, d;
// . . .
a = c+d;
a = b*a;
```

마찬가지로:

```cpp
a = b*(c+d);
```

가 같음

```cpp
a = b*(a=c+d);
```

두 번째 인코딩 각 추가 할당 연산 도입 하 고 따라서 가리킵니다 추가로 반올림 하기 때문에 이러한 인코딩을 해당 의미를 갖지 않습니다.

함수는 부동 소수점 값을 반환 하는 경우 함수 형식에 값을 반올림 됩니다. 함수에 부동 소수점 값을 매개 변수로 전달 될 때는 값 매개 변수의 형식으로 반올림 됩니다. 예를 들어:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

로 계산 됩니다.

```cpp
float sumsqr(float a, float b)
{
    register tmp3 = a*a;
    register tmp4 = b*b;
    register tmp5 = tmp3+tmp4;
    return (float) tmp5;
}
```

마찬가지로:

```cpp
float w, x, y, z;
double c;
...
c = symsqr(w*x+y, z);
```

로 계산 됩니다.

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>Fp 아래 아키텍처별 반올림: 정확 하 게

|프로세서|중간 식에 대 한 전체 자릿수를 반올림합니다.|
|-|-|
|x86|중간 식 16 비트 지 수에서 제공 하는 확장 된 범위와 기본 53 비트 전체 자릿수에서 계산 됩니다. 이러한 53:16 값은 "유출 되 는" 메모리를 (함수를 호출 하는 동안 발생할 수 있습니다), 11 비트 지 수 확장된 범위가 축소 됩니다. 즉, 이러한 값은 11 비트 지 수만 있는 배정밀도 표준 형식으로 캐스팅 됩니다.<br/>사용자가을 사용 하 여 부동 소수점 제어 단어를 변경 하 여 중간 반올림 하기 위해 확장 된 64 비트 정밀도로 전환할 수 있습니다 `_controlfp` FPU 환경 액세스할 수 있도록 설정 하 고 (참조 [fenv_access pragma](#the-fenv-access-pragma)). 그러나 확장 된 정밀도 레지스터 값은 유출 되는 메모리 때 이중 정밀도로 반올림 중간 결과가 됩니다.<br/>이 특정 의미 체계는 변경 될 수 있습니다.|
|amd64|Amd64에 FP 의미 체계는 다른 플랫폼 다소 다릅니다. 성능상의 이유로 중간 작업에서 사용할 수 있는 가장 넓은 정밀도 대신 피연산자 중 하나가의 너비가 가장 넓은 정밀도에 계산 됩니다.  피연산자 보다 넓은 정밀도 사용 하 여 계산 하는 계산을 적용할 사용자 하위 식에서 하나 이상의 피연산자는 캐스트 작업을 소개 하기 위해 필요 합니다.<br/>이 특정 의미 체계는 변경 될 수 있습니다.|

### <a name="algebraic-transformations-under-fpprecise"></a>Fp 아래 대 수 변환을: 정확 하 게

때 fp: precise 모드를 사용 하면 컴파일러 대 수 변환을 수행 하지 것입니다 *최종 결과 확실히 동일 하지 않으면*합니다. 다양 한 산술 실수에 대 한 친숙 한 대 수 규칙 유효 하지 않을 항상 부동 소수점 연산에 대 한 합니다. 예를 들어, 다음 식은 동일 Reals에 대 한 하지만 Float에 대 한 필요는 없습니다.

|Form|설명|
|-|-|
|`(a+b)+c = a+(b+c)`|연결 규칙 추가|
|`(a*b)*c = a*(b*c)`|곱하기에 대 한 결합형 규칙|
|`a*(b+c) = a*b + b*c`|더하기 곱하기의 배포|
|`(a+b)(a-b) = a*a-b*b`|예상 되는 대 수|
|`a/b = a*(1/b)`|역으로 나누기|
|`a*1.0 = a`|곱셈 id|

함수와 함께 소개 예제에 표시 된 대로 `KahanSum`, 컴파일러 상당히 빠르긴 프로그램을 생성 하기 위해 다양 한 대 수 변환을 수행 하려고 할 수 있습니다. 최적화 대 수 변환을에 종속 되지 않지만 거의 항상 올바른, 안전 하다는 경우가 있습니다. 예를 들어,으로 나누기를 대체 하는 것이 바람직한 경우가 됩니다는 *상수* 곱셈 역 곱하는 식은 상수를 사용 하 여 값:

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

로 변환 될 수 있습니다.

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

X는 최적화 프로그램이 컴파일 타임에 확인할 수 있으므로이 안전 변환 / 4.0 x*(1/4.0) 무한대 및 NaN를 포함 하 여 x의 모든 부동 소수점 값에 대 한 = = 합니다. 컴파일러는 곱하기와 나누기 연산을 대체 하 여 몇 회의 주기를 저장할 수-특히, 나누기를 구현 하지 않는 직접 하지만 조합한 역 근사값을 생성 하 곱하기 추가 컴파일러 필요 FPUs에서 지침입니다. 컴파일러에서 fp 최적화를 수행할 수 있습니다: 정확 하 게 대체 곱하기 정확한 생성 하는 경우에와 같은 결과 나누기입니다. 컴파일러에서 fp trivial 변환 수행 수도: precise, 결과 동일 제공 합니다. 여기에는 다음이 포함됩니다.

|Form|설명
|-|-|
|`(a+b) == (b+a)`|추가 대 한 누적 규칙|
|`(a*b) == (b*a)`|곱하기 위한 가환 적 규칙|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|1.0 곱하|
|`x/1.0*y == x*y/1.0 == x*y`|1.0으로 나누|
|`2.0*x == x+x`|2.0 곱하는 식은|

### <a name="contractions-under-fpprecise"></a>Fp 아래 축약: 정확 하 게

최신 부동 소수점 단위의 수의 핵심 아키텍처 기능은 뒤에 중간 반올림 오류 없이 단일 작업으로 추가 하 여 곱하기를 수행 하는 기능입니다. Intel의 Itanium 아키텍처 각 삼항 이러한 작업을 결합 하는 지침을 제공 하는 예를 들어 (한*b + c), (한*b c) 및 (c a * b), 부동 소수점 단일 명령으로 (fma, fms 및 fnma 각각). 이 단일 지침은 별도 실행을 보다 빠르게 곱하기 및 지침을 추가 되며 보다 정확 하 게 제품의 중간 적용 되지 않은 없으므로 있습니다. 크게이 최적화 곱하기 인터리빙 된 몇 가지를 포함 하는 함수를 단축 하 고 작업을 추가할 수 있습니다. 예를 들어 다음 알고리즘을 두 n 차원 벡터의 내적을 계산 하는 것이 좋습니다.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

이 계산을 수행할 수 수 곱하기 더하기 p 폼의 지시를 일련의 = p + x [i] * y [i].

축약형 최적화 독립적으로 제어할 수를 사용 하 여 `fp_contract` 컴파일러 pragma입니다. 기본적으로 fp: 속도 정확도 향상 시키는 이후 축약 정확한 모델을 사용 합니다. Fp 아래: precise, 컴파일러는 하지 계약 명시적 반올림 된 식입니다.
예제

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add
etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

### <a name="order-of-floating-point-expression-evaluation-under-fpprecise"></a>Fp에서 부동 소수점 식 평가 순서: 정확 하 게

부동 소수점 식 평가 순서를 유지 하는 최적화는 항상 안전 하 고 따라서 fp 허용: precise 모드입니다. 단 정밀도의 두 n 차원 벡터의 내적을 계산 하는 다음과 같은 함수가 있다고 합시다. 아래 첫 번째 코드 블록 원래 기능으로는 프로그래머가 인코딩될 수 다음 동일한 기능 부분 루프 줄이기와 최적화 후 됩니다.

```cpp
//original function
float dotProduct( float x[], float y[], int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}

//after a partial loop-unrolling
float dotProduct( float x[], float y[], int n )
{
   int n4= n/4*4; // or n4=n&(~3);
   float p=0;
   int i;

   for (i=0; i<n4; i+=4)
   {
      p+=x[i]*y[i];
      p+=x[i+1]*y[i+1];
      p+=x[i+2]*y[i+2];
      p+=x[i+3]*y[i+3];
   }

   // last n%4 elements
   for (; i<n; i++)
      p+=x[i]*y[i];

   return p;
}
```

이 최적화의 주요 이점은 75%에서 조건부 루프 분기의 수를 줄어든다는 것입니다. 또한 루프 본문 내에서 작업의 수를 늘려 컴파일러 수 이제 두 개 더 많은 기회를 추가로 최적화. 예를 들어, 일부 FPUs 수행할 수 수 있습니다는 p + =에서 곱하기 더하기 x [i] * [i] x [i + 1]에 대 한 값을 동시에 가져오는 동안 y 및 y [i + 1]는 다음 단계에서 사용 하기 위해 합니다. 이 유형의 최적화는 연산의 순서를 보존 하기 때문에 부동 소수점 계산에 안전 하 게 완벽 하 게 보호 합니다.

종종 컴파일러 빠른 코드를 생성 하기 위해 전체 작업 순서를 변경 하는 것이 유용 합니다. 다음 코드를 살펴보세요.

```cpp
double a, b, c, d;
double x, y, z;
...
x = a*a*a + b*b*b + c*c*c;
...
y = a*a + b*b + c*c;
...
z = a + b + c;
```

C + + 의미 체계 규칙에 표시 된 먼저 계산 하는 경우 프로그램 결과 생성 하도록 x, y 및 z. 컴파일러에 4 개 까지만 사용할 수 있는 부동 소수점 레지스터 가정 합니다. 컴파일러가 계산을 강제 적용 된 경우 x, y 및 z 순서 대로 다음과 같은 의미 체계를 사용 하 여 코드를 생성 하는 하도록 선택할 수:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute x
r0 = a;         // r1 = a*a*a
r1 = r0*r0;
r1 = r1*r0;
r0 = b;         // r2 = b*b*b
r2 = r0*r0;
r2 = r2*r0;
r0 = c;         // r3 = c*c*c
r3 = r0*r0;
r3 = r3*r0;
r0 = r1 + r2;
r0 = r0 + r3;
x = r0;         // x = r1+r2+r3
// . . .
// Compute y
r0 = a;         // r1 = a*a
r1 = r0*r0;
r0 = b;         // r2 = b*b
r2 = r0*r0;
r0 = c;         // r3 = c*c
r3 = r0*r0;
r0 = r1 + r2;
r0 = r0 + r3;
y = r0;         // y = r1+r2+r3
// . . .
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1 + r2;
r0 = r0 + r3;
z = r0;         // z = r1+r2+r3
```

이 인코딩은 명확 하 게 중복 몇 가지 작업은 없는 합니다. 컴파일러는 c + + 의미 체계 규칙 엄격 하 게 뒤,이 있으므로 순서는 필요한 프로그램 중간 FPU 환경 각 할당에 액세스할 수 있습니다. 그러나 fp에 대 한 기본 설정을: 정확한 컴파일러 최적화 프로그램은 환경에 액세스 하지 않는 것 처럼에 하므로 이러한 식의 순서를 변경 하 합니다. 반대 방향, 다음과 같은 세 가지 값을 계산 하 여는 중복 제거는 다음:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1+r2;
r0 = r0+r3;
z = r0;
...
// Compute y
r1 = r1*r1;
r2 = r2*r2;
r3 = r3*r3;
r0 = r1+r2;
r0 = r0+r3;
y = r0;
...
// Compute x
r0 = a;
r1 = r1*r0;
r0 = b;
r2 = r2*r0;
r0 = c;
r3 = r3*r0;
r0 = r1+r2;
r0 = r0+r3;
x = r0;
```

이 인코딩은 명확 하 게 뛰어난 거의 40 %fp 명령 수가 감소 것입니다. 결과 대 한 x, y 및 z는 동일한 이전 처럼 하지만 오버 헤드가 적은 계산 합니다.

Fp 아래: precise, 컴파일러 있을 수 있습니다 *인터레이스* 공통 하위 식 코드 속도 향상을 만들 수 있도록 합니다. 예를 들어, quadratic 방정식의 루트를 계산 하는 코드를 다음과 같이 작성 될 수 있습니다.

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

이러한 식은 한 번만 다른, 있지만 프로그래머가 수 있습니다 작성 한 가장 높은 실용적인 정밀도에서 각 루트 값을 계산할 수는 보장 하는이 방법은 합니다. Fp 아래: precise, 컴파일러는 인터레이스 root0 및 root1 정밀도 손실 없이 공통 하위 식 제거 하 여 계산을 위해 사용할 수 있습니다. 예를 들어, 다음은 제거 중복 된 몇 가지 단계 정확히 같은 결과 생성 하는 동안.

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

특정 독립 식의 평가 이동 하려면 다른 최적화를 시도할 수 있습니다. 루프 본문 내에서 조건부 분기를 포함 하는 다음 알고리즘을 고려해 야 합니다.

```cpp
vector<double> a(n);
double d, s;
// . . .
for (int i=0; i<n; i++)
{
   if (abs(d)>1.0)
      s = s+a[i]/d;
   else
      s = s+a[i]*d;
}
```

컴파일러를 검색할 수 있는 식의 값 (abs(d) > 1)는 루프 본문 내에서 고정 합니다. 이렇게 하면 "옮길" if 컴파일러 다음 위의 코드 변환 루프 본문 외부 문:

```cpp
vector<double> a(n);
double d, s;
// . . .
if (abs(d)>1.0)
   for (int i=0; i<n; i++)
      s = s+a[i]/d;
else
   for (int i=0; i<n; i++)
      s = s+a[i]*d;
```

변환 이후가 더 이상 조건부 분기 있으므로 루프의 전반적인 성능을 크게 향상 시킬 루프 본문 중 하나입니다. 이 유형의 최적화 안전 하다는 때문에 식의 평가 (abs(d) > 1.0) 다른 식을 무관 합니다.

FPU 환경 액세스 또는 부동 소수점 예외 시에도 흐름 의미 체계를 변경 하기 때문에 이러한 유형의 최적화 contraindicated 됩니다. 이러한 최적화는만 사용할 수 fp 아래: precise 모드 FPU 환경 액세스 및 부동 소수점 예외 의미 체계는 기본적으로 사용 하지 않으므로 합니다. FPU 환경에 액세스 하는 함수를 사용 하 여 같은 최적화를 명시적으로 비활성화할 수는 `fenv_access` 컴파일러 pragma입니다. 마찬가지로, 부동 소수점 예외를 사용 하 여 함수를 사용 해야는 `float_control(except ... )` 컴파일러 pragma (사용 또는 **/fp: 제외 하 고** 명령줄 스위치).

요약 하자면, fp: 정밀 모드에서는 최종 결과 변경 하지 않는지 인 조건에서 부동 소수점 식의 평가 순서를 변경 하려면 컴파일러와 결과 부동 소수점 예외 또는 FPU 환경에 의존 하지 않습니다.

### <a name="fpu-environment-access-under-fpprecise"></a>Fp 아래 FPU 환경 액세스: 정확 하 게

때 fp: precise 모드를 사용 하면 컴파일러에 프로그램에 액세스 또는 FPU 환경을 변경 하지 않는 것으로 가정 합니다. 이 가정을 컴파일러가 순서를 바꾸거나 fp에서 효율성을 개선 하려면 부동 소수점 연산 이동할 수 있도록 앞에서 설명한 대로: 정확 하 게 합니다.

일부 응용 프로그램 사용 하 여 부동 소수점 반올림 방향을 변경 될 수는 `_controlfp` 함수입니다. 예를 들어, 일부 응용 프로그램 위쪽 계산 및 동일한 계산을 두 번 수행 하 여 산술 연산에 오류 범위를 하위 먼저 음의 무한대 반올림 하는 동안 다음 양의 무한대 방향으로 반올림 합니다. FPU 반올림을 제어 하는 편리한 방법을 제공 하므로 프로그래머가 FPU 환경을 변경 하 여 반올림 모드를 변경 하려면 수도 있습니다. 다음 코드는 FPU 환경을 변경 하 여 부동 소수점 곱하기의 경계를 정확한 오류를 계산 합니다.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Fp 아래: precise, 컴파일러 항상 가정 기본 FPU 환경 최적화 프로그램에 대 한 호출을 무시 하려면 무료 이므로 `_controlfp` 위의 할당 cUpper 줄이고 cLower = =는 * b;이 해도 명확 하 게 잘못 된 결과가 생성 됩니다. 이러한 최적화를 방지 하려면 FPU 환경 액세스를 사용 하 여 사용 하도록 설정 된 `fenv_access` 컴파일러 pragma입니다.

다른 프로그램 FPU의 상태 단어를 확인 하 여 특정 부동 소수점 오류를 검색 하려고 할 수 있습니다. 예를 들어 다음 코드를 0으로 나누기 및 부정확 한 조건에 대 한 확인

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = r;
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Fp 아래: precise, 식 평가 순서를 변경 하는 최적화 기능이 변경 될 수 있습니다 특정 오류가 발생 하는 지점입니다. 상태 단어에 액세스 하는 프로그램을 사용 하 여 FPU 환경 액세스를 허용 해야는 `fenv_access` 컴파일러 pragma입니다.

자세한 내용은 섹션을 참조 하십시오. [fenv_access pragma](#the-fenv-access-pragma)합니다.

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Fp에서 부동 소수점 예외 의미 체계: 정확 하 게

기본적으로 부동 소수점 예외 의미 체계가 fp에서 비활성화: 정확 하 게 합니다. 대부분의 c + + 프로그래머는 시스템 또는 c + + 예외 사용 하지 않고 부동 소수점 예외 조건 처리를 선호 합니다. 또한 앞에서 설명한 대로 부동 소수점 예외 의미 체계를 사용 하지 않도록 설정 된 컴파일러 더 융통성 있게 부동 소수점 연산을 최적화 하는 경우. 사용 하 여는 **/fp: 제외 하 고** 스위치 또는 `float_control` fp를 사용 하는 경우에 부동 소수점 예외 의미 체계를 사용 하도록 설정 하려면 pragma: 정확한 모델입니다.

자세한 내용은 섹션을 참조 하십시오. [부동 소수점 예외 의미 체계를 사용 하도록 설정](#enabling-floating-point-exception-semantics)합니다.

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>부동 소수점 의미 체계를: fast 모드

컴파일러 완화 해당 fp 규칙: fast 모드를 설정 하는 경우: 부동 소수점 연산을 최적화 하는 경우 정확 하 게 사용 합니다. 이 모드는 컴파일러가 부동 소수점 정확도 및 정확성을 저하 시켜 속도 대 한 부동 소수점 코드를 추가로 최적화를 사용 합니다. 정확도 높은 부동 소수점 계산에 의존 하지 않는 프로그램: fast 모드를 사용 하 여 중요 한 속도 향상을 발생할 수 있습니다.

: Fast 부동 소수점 모드를 사용 하 여 사용할 수는 [/fp: fast](fp-specify-floating-point-behavior.md) 다음과 같은 명령줄 컴파일러 스위치:

> cl /fp: fast source.cpp

이 예제에서는 source.cpp 파일에 대 한 코드를 생성할 때: fast 의미 체계를 사용 하도록 컴파일러에 지시 합니다. : Fast 모델 사용 하 여 함수에서 함수 별로 호출 될 수도 있습니다는 `float_control` 컴파일러 pragma입니다.

자세한 내용은 섹션을 참조 하십시오. [float_control pragma](#the-float-control-pragma)합니다.

: Fast 모드에서는 컴파일러가 부동 소수점 계산의 정확도 변경 하는 최적화를 수행할 수 있습니다. 컴파일러 올바르게 반올림할 수 할당, 포인터로 변환 또는 함수 호출 및 중간 반올림 항상를 수행 하지 않습니다. 축약 등과 같은 부동 소수점 특정 최적화가 항상 설정 됩니다. 부동 소수점 예외 의미 체계 및 FPU 환경 민감도 사용할 수 없는 및 사용할 수 없습니다.

|: fast 의미 체계|설명
|-|-|
|의미 체계를 반올림합니다.|대입문 할당에 명시적으로 반올림 하 고 함수 호출을 무시 될 수 있습니다.<br/>성능 요구 사항에 따라 정밀도 등록 하는 보다 작음에서 중간 식 반올림 될 수 있습니다.|
|대 수 변형|컴파일러는 실수 연관, 분배 대 수;에 따라 식 변형할 수 있습니다. 이러한 변환은 정확 하 게 또는 정확 하다는 보장 되지 않습니다.|
|축약|항상 사용 하도록 설정 합니다. pragma에서 사용할 수 없습니다. `fp_contract`|
|부동 소수점 계산 순서|컴파일러 이러한 변경 내용이 최종 결과 변경 될 수 있는 경우에 부동 소수점 식의 평가 순서를 변경할 수 있습니다.|
|FPU 환경 액세스|사용 하지 않습니다. 사용할 수 없음|
|부동 소수점 예외 의미 체계|사용 하지 않습니다. 사용할 수 없음|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>의미 체계: fast에서 부동 소수점 식 반올림

Fp 달리:: fast 모델이 정확 하 게 모델에 가장 편리한 정밀도 중간 계산을 수행 합니다. 포인터로 변환에 할당을 반올림 하 고 함수 호출 항상 발생 하지 않을 수 있습니다. 예를 들어, 아래 첫 번째 함수에 도입 된 3 개의 단 정밀도 변수 (`C`, `Y` 및 `T`). 컴파일러는 유효한 형식 승격의 이러한 변수를 등록 하도록 선택할 수 있습니다 `C`, `Y` 및 `T` 배정밀 합니다.

원래 기능:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

레지스터 변수:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

이 예제에서는: fast 원래 함수의 의도 subverted 했습니다. 최종 결과 변수에 저장에 최적화 된 `sum`, 올바른 결과에서 매우 perturbed 수 있습니다.

: Fast에서 컴파일러는 소스 코드에서 지정 된 정밀도 이상 유지 하기 위해 일반적으로 시도 합니다. 그러나 경우에 따라 컴파일러 수도 중간 식에서 수행 하는 *전체 자릿수를 줄이려면* 소스 코드에서 지정 된 것 보다 합니다. 예를 들어, 아래 첫 번째 코드 블록 배정밀도 버전의 제곱근 함수를 호출합니다. : Fast 경우는 결과 및 피연산자는 함수의 명시적으로 캐스팅 하는 단 정밀도 같은 특정 상황에서 컴파일러는 호출 하면 배정밀도로 대체 하도록 선택할 수 있습니다 `sqrt` 단 정밀도 를호출하여`sqrtf`함수입니다. 캐스트 되도록 터 값 때문에 `sqrt` 및 들어오는 값은 단 정밀도로 반올림, 반올림 대신 변경 합니다. Sqrt에 들어오는 값이 이중 정밀도 값 컴파일러는이 변환을 수행 하는 경우 전체 자릿수 비트 절반까지 잘못 된 수 있습니다.

원래 함수

```cpp
double sqrt(double);
// . . .
double a, b, c;
float f1, f2;
// . . .
float length = (float)sqrt((float)(a*a + b*b + c*c));
float sum = (float) ((double)f1 + (double)f2);
```

최적화 된 함수

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
double tmp0 = a*a + b*b + c*c;
float tmp1 = tmp0;    // round of parameter value
float length = sqrtf(tmp1); // rounded sqrt result
float sum = f1 + f2;
```

하지만 정확도 낮아집니다이 최적화 수 특히 유용할 수와 같은 단일 전체 자릿수 내장 함수 버전을 제공 하는 프로세서를 대상으로 할 때 `sqrt`합니다. 방금 정확 하 게 경우 컴파일러에서 사용 가능한 최적화 작업 플랫폼과 컨텍스트에 따라 달라 집니다.

또한 컴파일러에 사용할 수 있는 모든 정밀도 수준에서 수행 될 수 있는 중간 계산의 정밀도 대 한 보장된 일관성 없는 있습니다. 컴파일러는 코드에 의해 지정 된 대로 전체 자릿수 수준이 적어도 유지 하려고 하지만: fast 하면 빠르거나 더 작은 컴퓨터 코드를 생성 하기 위해 다운 캐스트 중간 계산을 최적화 합니다. 예를 들어, 컴파일러는 단 정밀도로 중간 곱하기 중 일부를 반올림 하 위의 코드를 최적화할 수 있습니다.

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
float tmp0 = a*a;     // round intermediate a*a to single-precision
float tmp1 = b*b;     // round intermediate b*b to single-precision
double tmp2 = c*c;    // do NOT round intermediate c*c to single-precision
float tmp3 = tmp0 + tmp1 + tmp2;
float length = sqrtf(tmp3);
float sum = f1 + f2;
```

이러한 종류의 추가 반올림 중간 계산 중 일부를 수행 하는 낮은 정밀도 부동 소수점 같이 단위 SSE2를 사용 하 여 발생할 수 있습니다. : Fast 반올림의 정확도 따라서 플랫폼에 따라 달라 집니다. 프로세서가 두 개에 효과적 컴파일되지 않는 코드 반드시 다른 프로세서에 대 한 잘 작동 하지 않습니다. 속도 이점이 정확도 문제 경우 확인을 위해 사용자를 제외 됩니다.

: Fast 최적화가 특히 특정 기능에 대 한 문제가 있는 경우 부동 소수점 모드로 전환할 수 있는 로컬로 fp: 정확 하 게 사용 하는 `float_control` 컴파일러 pragma입니다.


### <a name="algebraic-transformations-under-fpfast"></a>대 수 변환을: fast에서

: Fast 모드 특정, 수행 하는 컴파일러를 사용 하면 안전 하지 않은 대 수 변환을 부동 소수점 식입니다. 예를 들어 다음과 같은 안전 하지 않은 최적화: fast에서 이용할 수 있습니다.

||||
|-|-|-|
|원본 코드|1 단계|2 단계
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

1 단계에서 컴파일러는 관찰 `z = y – a – b` 은 항상 0입니다. 기술적으로 유효 하지 않은 관찰 개체 이지만,: fast에서 허용 됩니다. 컴파일러는 다음 사용 된 모든 후속 z 변수에 대 한 상수 값 0을 전파합니다. 2 단계에서 컴파일러를 추가 하는 관찰 하 여 최적화 `x - 0 == x`, `x * 0 == 0`등입니다. 마찬가지로 이러한 결과이 따르면 엄격 하 게 잘못 된 경우에: fast에서 수 있는 합니다. 최적화 된 코드는 이제 훨씬 빠르게 하지만 상당히 덜 정확 하거나도 잘못 된 수도 있습니다.

다음 (안전 하지 않은) 대 수 규칙: fast 모드가 설정 된 경우 최적화 프로그램에서 이용할 수 있습니다.

|||
|-|-|
|Form|설명|
|`(a + b) + c = a + (b + c)`|연결 규칙 추가|
|`(a * b) * c = a * (b * c)`|곱하기에 대 한 결합형 규칙|
|`a * (b + c) = a * b + b * c`|더하기 곱하기의 배포|
|`(a + b)(a - b) = a * a - b * b`|예상 되는 대 수|
|`a / b = a * (1 / b)`|역으로 나누기|
|`a * 1.0 = a, a / 1.0 = a`|곱셈 id|
|`a ± 0.0 = a, 0.0 - a = -a`|덧셈 id|
|`a / a = 1.0, a - a = 0.0`|취소|

: Fast 최적화가 특히 특정 기능에 대 한 문제가 있는 경우 부동 소수점 모드로 전환할 수 있는 로컬로 fp: 정확 하 게 사용 하는 `float_control` 컴파일러 pragma입니다.

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>: Fast에서 부동 소수점 식 평가 순서

Fp 달리: precise,: fast 컴파일러가 코드 속도 향상을 만들 수 있도록 부동 소수점 연산의 순서 수 있게 합니다. 따라서 일부 최적화: fast에서 식의 의도 한 순서를 보존 하지 않습니다. 예를 들어, 두 개의 n 차원 벡터의 내적을 계산 하는 다음 함수를 살펴보세요.

```cpp
float dotProduct( float x[], float y[],
                  int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

: Fast에서 최적화 프로그램의 스칼라 감소가 수행 될 수 있습니다는 `dotProduct` 함수를 다음과 같이 변형 효과적으로 작동 합니다.

```cpp
float dotProduct( float x[], float y[],int n )
{
    int n4= n/4*4; // or n4=n&(~3);
    float p=0, p2=0, p3=0, p4=0;
    int i;

    for (i=0; i<n4; i+=4)
    {
        p+=x[i]*y[i];
        p2+=x[i+1]*y[i+1];
        p3+=x[i+2]*y[i+2];
        p4+=x[i+3]*y[i+3];
    }
    p+=p2+p3+p4;

    // last n%4 elements
    for (; i<n; i++)
    p+=x[i]*y[i];

    return p;
}
```

최적화 된 버전의 함수에서 4 개의 개별 제품 합계는 동시에 수행 하 고 함께 추가 됩니다. 이 최적화는 계산을 빠르게 수행할 수 있습니다는 `dotProduct` 뿐 하 여 대상 프로세서의 최종 결과 따라 4 배 정확 하지 않을 수 있으므로 쓸모에 대 한 합니다. 이러한 최적화를 단일 함수 또는 변환 단위에 대 한 특히 문제가 있으면 부동 소수점 모드 전환할 수 있는 로컬로 fp: 정확 하 게 사용 하는 `float_control` 컴파일러 pragma입니다.

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Fp: 부동 소수점 의미 체계에 대해 strict 모드

때 fp: strict 모드를 사용 하면 컴파일러가 해당 fp 모두 같은 규칙을 준수: 부동 소수점 연산을 최적화 하는 경우 정확 하 게 사용 합니다. 이 모드는 또한 부동 소수점 예외 의미 체계와 FPU 환경에 대 한 민감도 사용 하도록 설정 하 고 축약 같은 특정 최적화를 사용 하지 않도록 설정 합니다. 작업의 가장 엄격한 모드입니다.

Fp: 엄격한 부동 소수점 모드를 사용 하 여 사용할 수는 [/fp: strict](fp-specify-floating-point-behavior.md) 다음과 같은 명령줄 컴파일러 스위치:

> cl /fp: strict source.cpp

이 예제에서는 fp를 사용 하도록 컴파일러에 지시: source.cpp 파일에 대 한 코드를 생성할 때 엄격한 의미 합니다. Fp: 엄격한 모델로 사용 하 여 함수에서 함수 별로 호출 될 수도 있습니다는 `float_control` 컴파일러 pragma입니다.

자세한 내용은 섹션을 참조 하십시오. [float_control pragma](#the-float-control-pragma)합니다.

Fp 아래: strict 모드에서는 컴파일러가 부동 소수점 계산의 정확도 방해할 수 있는 모든 최적화 되지 수행 합니다. 컴파일러가 할당에서 올바르게 반올림할 항상 됩니다, 포인터로 변환 및 함수 호출, 고 중간 반올림 지속적으로 수행 됩니다 같은 정밀도에 FPU 레지스터입니다. 부동 소수점 예외 의미 체계 및 FPU 환경 민감도 기본적으로 활성화 됩니다. 컴파일러는 모든 경우에는 정확성을 보장할 수 없습니다 축약 같은 특정 최적화를 사용할 수 없습니다.

|fp: 엄격한 의미 체계|설명|
|-|-|
|의미 체계를 반올림합니다.|대입문 할당에 명시적으로 반올림 하 고 함수 호출<br/>중간 식 레지스터 정밀도에 평가 됩니다.<br/>Fp 동일: 정확 하 게|
|대 수 변형|엄격한 준수를 관련이, 분배 비 부동 소수점 대 수 변형을에 항상 보장 되지 않는 동일한 결과 생성 합니다.<br/>Fp 동일: 정확 하 게|
|축약|항상 사용할 수 없음|
|부동 소수점 계산 순서|컴파일러가 부동 소수점 식의 평가 순서를 변경 하지 않습니다.|
|FPU 환경 액세스|항상 사용 됩니다.|
|부동 소수점 예외 의미 체계|기본적으로 활성화되어 있습니다.|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Fp에서 부동 소수점 예외 의미 체계: strict

부동 소수점 예외 의미 체계가 활성화 fp에서 기본적으로: 엄격한 모델입니다. 이러한 의미 체계를 사용 하지 않도록 하려면 하나를 사용는 **/fp: 제외 하 고-** 전환 하거나 소개는 `float_control(except, off)` pragma입니다.

자세한 내용은 섹션을 참조 하십시오. [부동 소수점 예외 의미 체계를 사용 하도록 설정](#enabling-floating-point-exception-semantics) 및 [Pragma float_control](#the-float-control-pragma)합니다.

## <a name="the-fenvaccess-pragma"></a>Fenv_access pragma

사용법:

```cpp
#pragma fenv_access( [ on  | off ] )
```

[fenv_access](../../preprocessor/fenv-access.md) pragma 컴파일러가 FPU 플래그 테스트 및 FPU 모드가 변경 방해할 수 있는 특정 최적화를 확인 하도록 합니다. 때의 상태 `fenv_access` 사용 하지 않으면 컴파일러 간주 될 수 있는 기본 FPU 모드는 실제로 및 FPU 플래그 테스트 되지 않습니다. 기본적으로 환경 액세스 fp에 대 한 사용할 수 없습니다: precise 모드 것 활성화할 수 있습니다 명시적으로이 pragma를 사용 하 여 경우에 합니다. Fp 아래: strict, `fenv_access` 항상 활성화 되어 있으며 해제할 수 없습니다. : Fast, 아래 `fenv_access` 비활성화 항상 되 고 사용할 수 없습니다.

Fp에 설명 된 대로: 정확한 섹션 일부 프로그래머가 사용 하 여 부동 소수점 반올림 방향을 변경 될 수는 `_controlfp` 함수입니다. 예를 들어 산술 연산에서 위쪽 및 아래쪽 오류가 경계 계산을 위해 일부 프로그램 계산을 수행할 동일한을 두 번 먼저 음의 무한대 반올림 하는 동안 다음 양의 무한대 방향으로 반올림 하는 동안 합니다. FPU 반올림을 제어 하는 편리한 방법을 제공 하므로 프로그래머가 FPU 환경을 변경 하 여 반올림 모드를 변경 하려면 수도 있습니다. 다음 코드는 FPU 환경을 변경 하 여 부동 소수점 곱하기의 경계를 정확한 오류를 계산 합니다.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

해제 된 경우에 `fenv_access` pragma 컴파일러가 기본 FPU 환경 가정를; 따라서 최적화 프로그램은 호출을 무시 무료로 `_controlfp` 위의 할당을 줄이고 `cUpper = cLower = a*b`합니다. 그러나 사용 하는 경우 `fenv_access` 같은 최적화를 방지 합니다.

프로그램 특정 부동 소수점 오류를 검색 FPU 상태 단어를 확인할 수도 있습니다. 예를 들어 다음 코드를 0으로 나누기 및 부정확 한 조건에 대 한 확인

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

때 `fenv_access` 가 비활성화 컴파일러 재배열 따라서 FPU 상태 검사 가능 subverting 부동 소수점 식의 실행 순서입니다. 사용 하도록 설정 `fenv_access` 같은 최적화를 방지 합니다.

## <a name="the-fpcontract-pragma"></a>Fp_contract pragma

사용법:

```cpp
#pragma fp_contract( [ on | off ] )
```

Fp에 설명 된 대로: 감축을 정확 하 게 섹션은 최신 부동 소수점 단위의 수에 대 한 기본적인 아키텍처 기능입니다. 축약 뒤에 중간 반올림 오류 없이 단일 작업으로 추가 하 여 곱하기를 수행 하는 기능을 제공 합니다. 이 단일 지침은 별도 실행을 보다 빠르게 곱하기 및 지침을 추가 되며 보다 정확 하 게 제품의 중간 적용 되지 않은 없으므로 있습니다. 계약된 작업의 값을 계산 수 `(a*b+c)` 두 작업 모두 무한 정밀도로 계산 했으며 다음 반올림 마치는 가장 근접 한 부동 소수점 숫자입니다. 크게이 최적화 곱하기 인터리빙 된 몇 가지를 포함 하는 함수를 단축 하 고 작업을 추가할 수 있습니다. 예를 들어 다음 알고리즘을 두 n 차원 벡터의 내적을 계산 하는 것이 좋습니다.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

이 계산을 수행할 수 수 곱하기 더하기 폼의 지시를 일련의 `p = p + x[i]*y[i]`합니다.

[fp_contract](../../preprocessor/fp-contract.md) pragma 부동 소수점 식의 수축 수 있는지 여부를 지정 합니다. 기본적으로 fp: 속도 정확도 향상 시키는 이후 축약 precise 모드 허용 합니다. 축약: fast 모드에 대해 항상 설정 됩니다. 그러나 축약 오류 조건의 명시적 검색을 방해할 수 있으므로는 `fp_contract` pragma 항상 fp 아래에서 사용할 수 없음: strict 모드입니다. 수 있는 식의 예 때 수축는 `fp_contract` pragma를 사용할 수 있습니다.:

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

## <a name="the-floatcontrol-pragma"></a>Float_control pragma

**/fp: 정확한**, **/fp: fast**, **/fp: strict** 및 **/fp: 제외 하 고** 스위치는--각 파일에 대해 부동 소수점 의미 체계를 제어 합니다. 기초로 사용 됩니다. [float_control](../../preprocessor/float-control.md) pragma는 함수에서 함수 별로 이러한 컨트롤을 제공 합니다.

사용법:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

Pragma `float_control(push)` 및 `float_control(pop)` 각각 푸시 및 부동 소수점 모드와는 스택으로 예외 옵션의 현재 상태를 팝 합니다. 상태는 `fenv_access` 및 `fp_contract` pragma 영향을 받지 않는 `pragma float_control(push/pop)`합니다.

Pragma 호출 `float_control(precise, on)` 하면 및 `float_control(precise, off)` precise 모드 의미 체계 사용할 수 없게 됩니다. 마찬가지로, pragma `float_control(except, on)` 하면 및 `float_control(except, off)` 예외 의미 체계가 사용할 수 없게 됩니다. 예외 의미 체계가 정확한 의미는도 사용 하도록 설정 하는 경우에 사용할 수 있습니다. 때 선택적 `push` 인수가 있는 경우의 상태는 `float_control` 옵션 의미 체계를 변경 하기 전에 푸시됩니다.

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>함수에서 함수 별로 부동 소수점 의미 체계 모드 설정

명령줄 스위치는 4 개의 다른 부동 소수점 pragma를 설정 하기 위한 줄임 사실입니다. 함수에서 함수 별로 특정 부동 소수점 의미 체계 모드를 명시적으로 선택 하려면 각 옵션 부동 소수점 pragma는 다음 표에 설명 된 대로 선택 합니다.

||||||
|-|-|-|-|-|
||float_control(precise)|float_control(except)|fp_contract|fenv_access|
|/fp: strict|위치|위치|해제|위치|
|/fp: strict /fp: 제외 하 고-|위치|해제|해제|위치|
|/fp: 정확 하 게|위치|해제|위치|해제|
|/fp: precise /fp: 제외 하 고|위치|위치|위치|해제|
|/fp: fast|해제|해제|위치|해제|

예를 들어, 다음을 명시적으로 활성화: fast 의미 합니다.

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> 예외 의미 체계가 "precise" 의미 체계를 해제 하기 전에 해제 해야 합니다.

## <a name="enabling-floating-point-exception-semantics"></a>부동 소수점 예외 의미 체계를 사용 하도록 설정

0으로 나누기와 같은 특정 예외 부동 소수점 조건에는 하드웨어 예외 신호를 보내 FPU 발생할 수 있습니다. 부동 소수점 예외는 기본적으로 비활성화 됩니다. 부동 소수점 예외가와 FPU 제어 단어를 수정 하 여 설정 되는 `_controlfp` 함수입니다. 예를 들어 다음 코드에서는 0으로 나누기 부동 소수점 예외:

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

0으로 나누기 예외를 사용 하는 모든 나누기 연산을 0 분모 동일한 신호 FPU 예외가 발생 합니다.

FPU 제어 단어를 기본 모드를 복원 하려면 호출 `_controlfp(_CW_DEFAULT, ~0)`합니다.

와 부동 소수점 예외 의미 체계를 사용 하도록 설정 된 **/fp: 제외 하 고** 플래그 부동 소수점 예외를 설정 하면 동일 하지 않습니다. 부동 소수점 예외 의미 체계가 활성화 되어 있으면 컴파일러는 부동 소수점 모든 작업 예외를 throw 할 수 있습니다 가능성에 대 한 설명 해야 합니다. FPU는 별도 프로세서 단위로, 때문에 다른 단위에 대 한 지침과 FPU에서 실행 하는 지침을 수행할 수 있습니다.

부동 소수점 예외를 사용 하는 FPU 잘못 된 명령의 실행이 중단 되 고 예외 상황을 FPU 상태 단어를 설정 하 여 신호 됩니다. CPU가 다음 부동 소수점 명령에 도달 하면 먼저 보류 중인 FPU 예외가 있는지 확인 합니다. 보류 중인 예외가 있는 경우, 프로세서는 운영 체제에서 제공 하는 예외 처리기를 호출 하 여 것 포착 합니다. 즉, 부동 소수점 연산이 예외 상황을를 발견 하면 해당 하는 예외가 없습니다 검색할 수 있도록 다음 부동 소수점 작업이 실행 될 때까지 합니다. 예를 들어 다음 코드는 0으로 나누기 예외를 트래핑:

```cpp
double a, b, c;
// . . .
// ...unmasking of FPU exceptions omitted...
__try
{
   b/c; // assume c==0.0
   printf("This line shouldn't be reached when c==0.0\n");
   c = 2.0*b;
}
__except( EXCEPTION_EXECUTE_HANDLER )
{
   printf("SEH Exception Detected\n");
}
// . . .
```

0으로 나누기 조건 식에서 발생 하는 경우는 = b/c FPU 않습니다 트랩/raise 2.0 식의 다음 부동 소수점 연산 될 때까지 예외 * b. 그 결과 다음과 같습니다.

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

출력의 첫 번째 줄에 해당 하는 printf 된 도달해 서는 안 됩니다. 식 b/c에서 발생 하는 부동 소수점 예외 실행 2.0에 도달할 때까지 발생 되지 않은 때문에 도달한 * b. B/c를 실행 한 직후 예외를 발생 시키기 위해 컴파일러 "wait" 명령을 정의 해야 합니다.

```cpp
// . . .
   __try
   {
      b/c; // assume this expression will cause a "divide-by-zero" exception
      __asm fwait;
      printf("This line shouldn't be reached when c==0.0\n");
      c = 2.0*b;
   }
// . . .
```

이 "wait" 명령 FPU의 상태와 동기화 되 고 있는 보류 중인 예외를 처리 하면 프로세서가 강제로 수행 합니다. 컴파일러는만 생성 하며 이러한 부동 소수점 의미 체계가 활성화 하는 경우 지침을 "wait"입니다. 이러한 의미 체계를 해제 하면 기본적으로는, 프로그램 부동 소수점 예외를 사용 하는 경우 위의 있는 것과 유사한 synchronicity 오류가 발생 합니다.

부동 소수점 의미 체계가 활성화 되어 있으면 컴파일러만 "wait" 지침 생기지, 컴파일러에서 불법으로 가능한 예외 시에도 부동 소수점 코드를 최적화할 수도 없게 됩니다. 이 예외가 throw 되는 지점을 변경 하는 모든 변환이 포함 됩니다. 이러한 요인으로 인해 부동 소수점 의미 체계를 사용 하면는 하므로 응용 프로그램의 성능이 저하 되는 생성 된 기계어 코드의 효율성이 감소할 상당히 수 있습니다.

부동 소수점 예외 의미 체계가 fp 아래에 기본적으로 활성화: strict 모드입니다. Fp에 이러한 의미 체계를 사용 하도록 설정 하려면: precise 모드 추가 **/fp: 제외한** 명령줄 컴파일러로 전환 합니다. 부동 소수점 예외 의미 체계가 사용 될 수 있고 사용 하 여 함수에서 함수 별로 사용 하지 않도록 설정 된 `float_control` pragma입니다.

### <a name="floating-point-exceptions-as-c-exceptions"></a>C + + 예외로 부동 소수점 예외

모든 하드웨어 예외와 부동 소수점 예외 기본적으로 c + + 예외를 일으키지 않습니다 하지만 대신 구조적된 예외를 트리거합니다. 부동 소수점 구조화 된 예외가 c + + 예외를 매핑하려면 사용자는 사용자 지정 SEH 예외 변환기를 제공할 수 있습니다. 를 소개 하 고 각 부동 소수점 예외에 해당 하는 c + + 예외:

```cpp
class float_exception : public std::exception {};

class fe_denormal_operand : public float_exception {};
class fe_divide_by_zero : public float_exception {};
class fe_inexact_result : public float_exception {};
class fe_invalid_operation : public float_exception {};
class fe_overflow : public float_exception {};
class fe_stack_check : public float_exception {};
class fe_underflow : public float_exception {};
```

그런 다음 부동 소수점 SEH 예외를 찾아 해당 하는 c + + 예외가 throw 됩니다 변환 함수를 소개 합니다. 이 함수를 사용 하려면 설정에 현재 프로세스 스레드에 대해 구조적 예외 처리기 변환기는 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) 런타임 라이브러리에서 함수입니다.

```cpp
void se_fe_trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )
{
    switch (u)
    {
    case STATUS_FLOAT_DENORMAL_OPERAND:   throw fe_denormal_operand();
    case STATUS_FLOAT_DIVIDE_BY_ZERO:     throw fe_divide_by_zero();
   etc...
    };
}
// . . .
_set_se_translator(se_fe_trans_func);
```

이 매핑은 초기화 되 면 부동 소수점 예외는 c + + 예외는 것 처럼 작동 합니다. 예를 들어:

```cpp
try
{
   // floating-point code that might throw divide-by-zero
   // or other floating-point exception
}
catch(fe_divide_by_zero)
{
    cout << "fe_divide_by_zero exception detected" << endl;
}
catch(float_exception)
{
    cout << "float_exception exception detected" << endl;
}
```

## <a name="references"></a>참조

[모든 컴퓨터 과학자 알아야 사항 부동 소수점 연산](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf) David 길동 여 합니다.

## <a name="see-also"></a>참고자료

[코드 최적화](optimizing-your-code.md)<br/>
