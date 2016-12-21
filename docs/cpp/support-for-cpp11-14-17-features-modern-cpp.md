---
title: "C++11/14/17 기능에 대한 지원(최신 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd2d5cbc-caf5-4a11-a057-8c365decba4e
caps.latest.revision: 59
caps.handback.revision: 56
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++11/14/17 기능에 대한 지원(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 Visual C\+\+의 C\+\+11\/14\/17 기능에 대해 설명합니다.  
  
##  <a name="top"></a> 이 문서의 내용  
  
-   [C++11 기능 목록](#featurelist)  
  
    -   [C++11 핵심 언어 기능 표](#corelanguagetable)  
  
    -   [C++11 핵심 언어 기능 표: 동시성](#concurrencytable)  
  
    -   [C++11 핵심 언어 기능: C99](#c99table)  
  
-   [C++14 핵심 언어 기능](#cpp14table)  
  
-   [C++17 제안된 핵심 언어 기능](#cpp17table)  
  
-   [기능 테이블 가이드](#tableguide)  
  
    -   [Rvalue 참조](#rvref)  
  
    -   [람다](#lambdas)  
  
    -   [decltype](#decltype)  
  
    -   [강력한 형식/전방 선언 열거형](#stronglytyped)  
  
    -   [맞춤](#alignment)  
  
    -   [표준 레이아웃 및 Trivial 형식](#standardlayout)  
  
    -   [기본 설정 및 삭제된 함수](#defaultedanddeleted)  
  
    -   [override 및 final](#overrideandfinal)  
  
    -   [원자성 등](#atomics)  
  
    -   [C99 __func__ 및 전처리기 규칙](#c99)  
  
-   [표준 라이브러리 기능](#stl)  
  
##  <a name="featurelist"></a> C\+\+11 기능 목록  
 Visual C\+\+는 [C\+\+11 핵심 언어 사양](http://go.microsoft.com/fwlink/p/?LinkID=235092)에 포함된 대부분의 기능과 많은 C\+\+14 라이브러리 기능 및 C\+\+17에 대해 제안된 일부 기능을 구현합니다. 다음 표에서는 Visual Studio 2010, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] 및 Visual Studio 2015의 Visual C\+\+에서 C\+\+11\/14\/17 핵심 언어 기능 및 해당 구현 상태를 보여 줍니다.  
  
###  <a name="corelanguagetable"></a> C\+\+11 핵심 언어 기능 표  
  
|[C\+\+11 핵심 언어 기능](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2869.html)|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|--------------------------------------------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|Rvalue 참조 [v0.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1610.html), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n2118.html), [v2.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2844.html), [v2.1](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html), [v3.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3053.html)|v2.0|v2.1\*|v2.1\*|v3.0|  
|[ref\-qualifiers](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2439.htm)|아니요|아니요|아니요|예|  
|[비정적 데이터 멤버 이니셜라이저](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2756.htm)|아니요|아니요|[예](../cpp/uniform-initialization-and-delegating-constructors.md)|예|  
|Variadic 템플릿 [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2242.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2555.pdf)|아니요|아니요|[예](../cpp/ellipses-and-variadic-templates.md)|예|  
|[이니셜라이저 목록](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2672.htm)|아니요|아니요|[예](../cpp/uniform-initialization-and-delegating-constructors.md)|예|  
|[static\_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1720.html)|예|예|예|예|  
|auto [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1984.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2546.htm)|v1.0|v1.0|v1.0|예|  
|[후행 반환 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2541.htm)|예|예|예|예|  
|람다 [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2550.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2658.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2927.pdf)|v1.0|v1.1|v1.1|예|  
|decltype [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2343.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3276.pdf)|v1.0|v1.1\*\*|v1.1|예|  
|[오른쪽 꺾쇠 괄호](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1757.html)|예|예|예|예|  
|[함수 템플릿의 기본 템플릿 인수](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html)|아니요|아니요|예|예|  
|[Expression SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|아니요|아니요|아니요|아니요|  
|[별칭 템플릿](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2258.pdf)|아니요|아니요|[예](../cpp/aliases-and-typedefs-cpp.md)|예|  
|[Extern 템플릿](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1987.htm)|예|예|예|예|  
|[nullptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2431.pdf)|예|예|예|예|  
|[강력한 형식의 열거형](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2347.pdf)|Partial|예|예|예|  
|[전방 선언 열거형](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2764.pdf)|아니요|예|예|예|  
|[특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2761.pdf)|아니요|아니요|아니요|예|  
|[constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2235.pdf)|아니요|아니요|아니요|예|  
|[맞춤](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2341.pdf)|TR1|Partial|Partial|예|  
|[위임 생성자](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1986.pdf)|아니요|아니요|[예](../cpp/uniform-initialization-and-delegating-constructors.md)|예|  
|[상속 생성자](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2540.htm)|아니요|아니요|아니요|예|  
|[명시적 변환 연산자](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2437.pdf)|아니요|아니요|예|예|  
|[char16\_t\/char32\_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2249.html)|아니요|아니요|아니요|예|  
|[유니코드 문자열 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|아니요|아니요|아니요|예|  
|[원시 문자열 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|아니요|아니요|[예](../cpp/string-and-character-literals-cpp.md)|예|  
|[리터럴의 유니버설 문자 이름](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2170.html)|아니요|아니요|아니요|예|  
|[사용자 정의 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2765.pdf)|아니요|아니요|아니요|예|  
|[표준 레이아웃 및 Trivial 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2342.htm)|아니요|예|예|예|  
|[기본 설정 및 삭제된 함수](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2346.htm)|아니요|아니요|[예\*](../cpp/explicitly-defaulted-and-deleted-functions.md)|예|  
|[확장된 friend 선언](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1791.pdf)|예|예|예|예|  
|[확장된 sizeof](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2253.html)|아니요|아니요|아니요|예|  
|[인라인 네임스페이스](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2535.htm)|아니요|아니요|아니요|예|  
|[무제한 공용 구조체](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2544.pdf)|아니요|아니요|아니요|예|  
|[로컬 및 명명되지 않은 형식을 템플릿 인수로 사용](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2657.htm)|예|예|예|예|  
|[Range\-based for 루프](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2930.html)|아니요|예|예|예|  
|override 및 final [v0.8](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2928.htm), [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3206.htm), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3272.htm)|Partial|예|예|예|  
|[최소한의 GC 지원](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2670.htm)|예|예|예|예|  
|[noexcept](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3050.html)|아니요|아니요|아니요|예|  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="concurrencytable"></a> C\+\+11 핵심 언어 기능 표: 동시성  
  
|C\+\+11 핵심 언어 기능: 동시성|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|---------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[다시 표시된 시퀀스 위치](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2239.html)|N\/A|N\/A|N\/A|예|  
|[원자성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2427.html)|아니요|예|예|예|  
|[강력한 비교 및 교환](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2748.html)|아니요|예|예|예|  
|[양방향 펜스](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2752.htm)|아니요|예|예|예|  
|[메모리 모델](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2429.htm)|N\/A|N\/A|N\/A|예|  
|[데이터 종속성 순서 지정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2664.htm)|아니요|예|예|예|  
|[데이터 종속성 순서 지정: 함수 주석](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2782.htm)|아니요|아니요|아니요|예|  
|[exception\_ptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2179.html)|예|예|예|예|  
|[quick\_exit](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2440.htm)|아니요|아니요|아니요|예|  
|[신호 처리기의 원자성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2547.htm)|아니요|아니요|아니요|아니요|  
|[스레드 로컬 저장소](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2659.htm)|Partial|Partial|Partial|예|  
|[매직 정적 이름](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2660.htm)|아니요|아니요|아니요|예|  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="c99table"></a> C\+\+11 핵심 언어 기능: C99  
  
|C\+\+11 핵심 언어 기능: C99|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|---------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[\_\_func\_\_](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2340.htm)|Partial|Partial|Partial|예|  
|[C99 전처리기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Partial|Partial|Partial|Partial|  
|[long long](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1811.pdf)|예|예|예|예|  
|[확장된 정수 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|N\/A|N\/A|N\/A|N\/A|  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="cpp14table"></a> C\+\+14 핵심 언어 기능  
  
||||  
|-|-|-|  
|기능|Visual Studio 2013|Visual Studio 2015|  
|컨텍스트 변환에 대해 조정된 작업|예|예|  
|이진 리터럴|아니요|예|  
|auto 및 decltype\(auto\) 반환 형식|아니요|예|  
|init 캡처|아니요|예|  
|제네릭 람다|아니요|예|  
|변수 템플릿|아니요|아니요|  
|확장된 constexpr|아니요|아니요|  
|집합체에 대한 NSDMI|아니요|아니요|  
|할당 방지\/융합|아니요|아니요|  
|\[\[deprecated\]\] 특성|아니요|아니요|  
|크기가 지정된 할당|아니요|예|  
|자릿수 구분 기호|아니요|예|  
  
###  <a name="cpp17table"></a> C\+\+17 제안된 핵심 언어 기능  
  
||||  
|-|-|-|  
|기능|Visual Studio 2013|Visual Studio 2015|  
|중괄호로 묶인 Init 목록을 사용한 auto에 대한 새 규칙|아니요|아니요|  
|간결한 정적 어설션|아니요|아니요|  
|템플릿 template\-parameters의 typename|아니요|아니요|  
|삼중자 제거|예|예|  
|중첩된 네임스페이스 정의|아니요|아니요|  
|N4259 std::uncaught\_exceptions\(\)|아니요|아니요|  
|N4261 한정 변환 수정|아니요|아니요|  
|N4266 네임스페이스 및 열거자에 대한 특성|아니요|아니요|  
|N4267 u8 문자 리터럴|아니요|아니요|  
|N4268 더 많은 비형식 템플릿 인수 허용|아니요|아니요|  
|N4295 식 폴딩|아니요|아니요|  
|await\/resume|아니요|예|  
  
##  <a name="tableguide"></a> 기능 테이블 가이드  
  
###  <a name="rvref"></a> Rvalue 참조  
  
> [!NOTE]
>  다음 설명의 버전 지정\(v0.1, v1.0, v2.0, v2.1, v3.0\)은 단순히 C\+\+11의 발전을 보여주기 위해 만든 것입니다. 표준 자체에서는 사용하지 않습니다.  
  
 [N1610 "rvalue로 클래스 개체 초기화 확인"](http://go.microsoft.com/fwlink/p/?LinkID=235093)은 rvalue 참조 없이 초기에 이동 의미 체계를 사용하려 했습니다.  설명을 위해 "rvalue 참조 v0.1"이라고 하겠습니다. "rvalue 참조[v1.0](http://go.microsoft.com/fwlink/p/?LinkID=235094)"으로 대체되었습니다. Visual Studio 2010의 Visual C\+\+ 작업이 기반으로 하는 "Rvalue 참조 [v2.0](http://go.microsoft.com/fwlink/p/?LinkID=235095)"에서는 rvalue 참조가 lvalue에 바인딩하지 못하도록 하여 주요 안전 문제를 해결합니다.  "Rvalue 참조 [v2.1](http://go.microsoft.com/fwlink/p/?LinkID=235096)"에서 이 규칙을 구체적으로 지정합니다.  오버로드 `push_back(const string&)` 및 `push_back(string&&)`를 갖는 `vector<string>::push_back()`를 고려하고 `v.push_back("strval")`을 호출합니다.`"strval"` 식은 문자열 리터럴이며 lvalue입니다.  \(다른 리터럴, 예를 들어 정수 1729는 rvalue이지만, 문자열 리터럴은 배열이므로 특수합니다.\)  "rvalue 참조 v2.0" 규칙에는 `string&&`이 lvalue이기 때문에 `"strval"`를 `"strval"`에 바인딩할 수 없다고 되어 있으므로 `push_back(const string&)`이 유일한 후보 오버로드입니다.  그러면 효율적이지 않은 방식으로 임시 `std::string`을 만들고, 이를 벡터에 복사한 후 임시 `std::string`을 삭제합니다. "rvalue 참조 v2.1" 규칙은 `string&&`의 `"strval"`에 대한 바인딩이 임시 `std::string`를 만들고 이 임시 값이 rvalue임을 인식합니다.  따라서 `push_back(const string&)` 및 `push_back(string&&)` 둘 다 후보이며 `push_back(string&&)`이 선호됩니다.  임시 `std::string`이 생성된 다음 벡터로 이동합니다.  이 방식이 더 효율적입니다.  
  
 "Rvalue 참조 [v3.0](http://go.microsoft.com/fwlink/p/?LinkID=235097)"은 특정 조건에서 이동 생성자를 자동으로 생성하고 할당 연산자를 이동하는 새 규칙을 추가합니다. Visual Studio 2015에서 구현되었습니다.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="lambdas"></a> 람다  
 [람다 함수](../cpp/lambda-expressions-in-cpp.md)가 작업 용지\([버전 "0.9"](http://go.microsoft.com/fwlink/p/?LinkID=235098)\)로 가결되고 변형 가능한 람다가 추가\([버전 "1.0"](http://go.microsoft.com/fwlink/p/?LinkID=235099)\)된 후 표준화 위원회에서 단어를 점검했습니다. 이를 통해 [버전 "1.1"](http://go.microsoft.com/fwlink/p/?LinkID=235100) 람다가 생성되었지만 이 람다는 현재 완벽하게 지원되지 않습니다.  V1.1 람다 표현은 정적 멤버 또는 중첩된 람다 식과 같은 코너 케이스에서 발생하는 것을 명확히 보여 줍니다.  이 표현은 복잡한 람다에서 발생하는 문제를 해결합니다.  또한 이제 상태 비저장 람다를 함수 포인터로 변환할 수 있습니다.  N2927 표현에는 없지만 람다 v1.1에 포함된 것으로 간주됩니다.[C\+\+11](http://go.microsoft.com/fwlink/p/?LinkID=235092)**5.1.2 \[expr.prim.lambda\]\/6**에는 다음과 같은 설명이 포함되어 있습니다. "`lambda-capture`가 없는 `lambda-expression`의 클로저 형식에는 클로저 형식의 함수 호출 연산자와 동일한 매개 변수 및 반환 형식을 가진 함수 포인터에 대한 공용 비가상 비명시적 상수 변환 함수가 있습니다. 이 변환 함수로 반환되는 값은 호출된 경우 클로저 형식의 함수 호출 연산자를 호출하는 것과 동일한 효과를 갖는 함수 주소여야 합니다."  \(임의의 호출 규칙을 가진 함수 포인터로 변환 가능한 상태 비저장 람다를 만들므로 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] 구현이 훨씬 효율적입니다.\)  이는 `__stdcall`과 같은 함수 포인터가 필요한 API를 사용할 경우 중요합니다.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="decltype"></a> decltype  
 작업 용지\([버전 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235101)\)에 decltype이 가결된 후, 릴리스 바로 전에 작지만 중요한 해결책을 받았습니다\([버전 1.1](http://go.microsoft.com/fwlink/p/?LinkID=235102)\).  STL 및 Boost로 작업하는 프로그래머에게 흥미로운 내용입니다.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="stronglytyped"></a> 강력한 형식\/전방 선언 열거형  
 [강력한 형식의 열거형](http://go.microsoft.com/fwlink/p/?LinkID=235103)은 Visual Studio 2010의 Visual C\+\+에서 부분적으로 지원되었습니다\(특히 명시적으로 지정되는 기본 형식\). 이제 Visual Studio에서 완전히 구현되며 [전방 선언 열거형](http://go.microsoft.com/fwlink/p/?LinkID=235104)에 대한 C\+\+11 의미 체계도 완전히 구현됩니다.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="alignment"></a> 맞춤  
 작업 용지에 기표되는 [조정 제안서](http://go.microsoft.com/fwlink/p/?LinkID=235105)의 핵심 언어 키워드 `alignas`\/`alignof`가 Visual Studio 2015에서 구현되었습니다.  Visual Studio 2010의 Visual C\+\+에는 TR1의 `aligned_storage`가 포함되었습니다.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]은 `aligned_union` 및 `std::align()`을 표준 라이브러리에 추가하였고, [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 중요한 문제가 수정되었습니다.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="standardlayout"></a> 표준 레이아웃 및 Trivial 형식  
 [N2342 "POD's Revisited; Resolving Core Issue 568 \(Revision 5\)"](http://go.microsoft.com/fwlink/p/?LinkID=235106)의 노출된 변경은 `is_trivial` 및 `is_standard_layout`을 표준 템플릿 라이브러리의 `<type_traits>`에 추가합니다.  \(N2342에서 핵심 언어의 많은 단어를 재작업했지만 컴파일러 변경은 필요하지 않습니다.\)  이러한 형식 특성은 Visual Studio 2010의 Visual C\+\+에서 사용할 수 있었지만 `is_pod`은 중복되었습니다. 그러므로 이 문서 앞 부분의 표에는 지원되지 않는 것으로 나와 있습니다.  이제는 정확한 답을 제공하도록 설계된 컴파일러 후크를 사용할 수 있습니다.  
  
 STL의 [common\_type\<\>](../standard-library/common-type-class.md)은 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 매우 필요한 수정 프로그램을 받았습니다.`common_type<>`에 대한 C\+\+11 사양에 예기치 않은 결과가 발생했습니다. 특히 `common_type<int, int>::type`은 `int&&`를 반환합니다. 따라서 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]은 [Proposed Resolution for Library Working Group issue 2141](http://go.microsoft.com/fwlink/p/?LinkId=320075)을 구현하며 이를 통해 `common_type<int, int>::type`은 `int`를 반환합니다.  
  
 이 변경의 부작용으로 ID의 경우가 더 이상 작동하지 않습니다\(`common_type<T>`가 `T` 형식을 생성하지 않는 경우도 있음\). 이는 제안된 해결 방법을 사용하여 컴파일되지만 이전 동작에 의존하는 모든 코드가 중단됩니다.  
  
 ID 형식 특성이 필요한 경우 `std::identity`에 정의된 비표준 `<type_traits>`는 `<void>`에 대해 작동하지 않으므로 사용하지 마세요. 대신 필요에 따라 고유한 ID 형식 특성을 구현합니다. 예를 들면 다음과 같습니다.  
  
```cpp  
template <typename T> struct Identity { typedef T type; };  
  
```  
  
> [!NOTE]
>  기타 주요 변경 내용은 [Visual C\+\+ 2015의 주요 변경 내용](../porting/visual-cpp-change-history-2003-20151.md)을 참조하세요.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="defaultedanddeleted"></a> 기본 설정 및 삭제된 함수  
 이제 지원되지만 다음 예외가 발생합니다. 기본 함수의 경우 멤버 이동 생성자 및 이동 할당 연산자를 요청하기 위한 `=default` 사용은 지원되지 않습니다. 복사 및 이동이 표준에서 지정한 대로 정확하게 상호 작용하지 않습니다. 예를 들어 이동 삭제는 복사도 비활성화하도록 지정되지만 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]는 그렇지 않습니다.  
  
 기본 설정 및 삭제된 함수를 사용하는 방법에 대한 자세한 내용은 [함수](../cpp/functions-cpp.md)를 참조하세요.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="overrideandfinal"></a> override 및 final  
 이 과정은 짧지만 복잡한 진화였습니다. 원래 [버전 0.8](http://go.microsoft.com/fwlink/p/?LinkID=235108)에는 \[\[`override`\]\], \[\[`hiding`\]\] 및 \[\[`base_check`\]\] 특성이 있었습니다.[버전 0.9](http://go.microsoft.com/fwlink/p/?LinkID=235109)에서는 이 특성이 제거되어 컨텍스트 키워드로 대체되었습니다.  마지막으로 [버전 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235110)에서는 클래스의 "`final`", 함수의 "`override`" 및 "`final`"로 축소되었습니다.  Visual Studio 2010의 Visual C\+\+에서는 이미 이 "`override`" 구문이 함수에서 지원되고 C\+\+11과 상당히 비슷한 의미 체계를 갖기 때문에 이를 Ascended 확장으로 설정합니다.  "`final`"도 지원되지만 스펠링이 다른 "sealed"에서 사용한 경우입니다.  "`override`" 및 "`final`"의 표준 철자와 의미 체계가 이제 완전하게 지원됩니다. 자세한 내용은 [override 지정자](../cpp/override-specifier.md) 및 [final 지정자](../cpp/final-specifier.md)를 참조하세요.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="atomics"></a> 원자성 등  
 [원자성](http://go.microsoft.com/fwlink/p/?LinkID=235111), [강력한 비교 및 교환](http://go.microsoft.com/fwlink/p/?LinkID=235112), [양방향 펜스](http://go.microsoft.com/fwlink/p/?LinkID=235113) 및 [데이터 종속 순서지정](http://go.microsoft.com/fwlink/p/?LinkID=235114)에서는 구현이 완료된 표준 라이브러리 시스템을 지정합니다.  
  
 **관련 STL 헤더:** [\<atomic\>](../standard-library/atomic.md), [\<chrono\>](../standard-library/chrono.md), [\<condition\_variable\>](../standard-library/condition-variable.md), [\<future\>](../standard-library/future.md), [\<mutex\>](../standard-library/mutex.md), [\<ratio\>](../standard-library/ratio.md), [\<scoped\_allocator\>](../standard-library/scoped-allocator.md), and [\<thread\>](../standard-library/thread.md).  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="c99"></a> C99 \_\_func\_\_ 및 전처리기 규칙  
 [C++11 핵심 언어 기능: C99](#c99table)표에는 항목에 대한 "부분" 구현이 나열됩니다. 사전 정의된 식별자인 `__func__`의 경우 비표준 확장 `__FUNCDNAME__`, `__FUNCSIG__` 및 `__FUNCTION__`만 지원되므로 "부분"이 표시됩니다. 자세한 내용은 [미리 정의된 매크로](../preprocessor/predefined-macros.md)을 참조하세요. C99 전처리기 규칙의 경우 *variadic 매크로*가 지원되므로 "부분"이 표시됩니다. 자세한 내용은 [Variadic 매크로](../preprocessor/variadic-macros.md)을 참조하세요.  
  
 \[[이 문서의 내용](#top)\]  
  
###  <a name="stl"></a> 표준 라이브러리 기능  
 핵심 언어를 다룹니다. C\+\+11 표준 라이브러리의 경우 마땅한 기능 비교 표는 없지만 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]에서 이를 구현했습니다\(단, 두 가지 예외가 있음\).  먼저 라이브러리 기능이 컴파일러에 없는 기능에 종속되면 시뮬레이션되었거나\(예: `make_shared<T>()`의 경우 시뮬레이션된 variadic 템플릿\) 구현되지 않은 것입니다. \(특히 `<initializer_list>`를 포함하여 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 완전히 구현된 몇 가지 사례만 있습니다.\)  거의 예외 없이 C99는 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] 및 제공된 C\+\+ 래퍼 헤더에 구현되었습니다. 자세한 내용은 [Visual Studio 2013의 C99 라이브러리 지원](http://go.microsoft.com/fwlink/p/?LinkId=321308)\(영문\)을 참조하세요.  
  
 다음은 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] 및 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]의 일부 변경 사항 목록입니다.  
  
 **Emplacement:** C\+\+11에 필요하기 때문에 "임의" 개수의 인수에 대해 모든 컨테이너에서 `emplace()`\/`emplace_front()`\/`emplace_back()`\/`emplace_hint()`\/`emplace_after()`가 구현되었습니다\("시뮬레이션된 variadics" 단원 참조\).  예를 들어, `vector<T>`에는 완벽하게 전달된 임의 개수의 임의 인수에서 벡터 뒤에 T 형식의 요소를 직접 생성하는 "`template <typename... Args> void emplace_back(Args&&... args)`"이 있습니다.  이는 추가 이동 생성 및 소멸을 포함하는 `push_back(T&&)`보다 더 효과적일 수 있습니다.  
  
 **Variadics:** [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]에는 variadic 템플릿을 시뮬레이트하기 위한 스키마가 포함되었습니다.[!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서 시뮬레이션이 사라지고 **variadics가 완전히 구현됩니다**. 코드가 예전에 시뮬레이션된 variadics 동작에 의존하는 경우 수정해야 합니다. 그러나 실제 variadic 템플릿으로 전환하면 **컴파일 시간 향상** 및 **컴파일러 메모리 소비 감소**가 발생합니다.  
  
 **명시적 변환 연산자:** 핵심 언어에서 명시적 변환 연산자는 일반적인 기능입니다. 예를 들어 `explicit operator MyClass()`를 가질 수 있습니다. 그러나 표준 라이브러리는 현재 `explicit operator bool()` 폼 하나만 사용합니다. 클래스를 안전하게 부울 테스트할 수 있기 때문입니다. \(일반 "`operator bool()`"은 매우 위험합니다.\) 이전에는 Visual C\+\+이 `operator pointer-to-member()`를 사용하여 `explicit operator bool()`를 시뮬레이트했으므로 다양한 문제가 발생했고 효율성이 부족한 면이 있었습니다. 이제, "가짜 bool" 해결 방법은 완전히 제거됩니다.  
  
 **임의성:** `uniform_int_distribution`는 이제 완벽하게 공평성을 지니고 `shuffle()`이 `<algorithm>`에 구현되어 `mersenne_twister` 같은 Uniform Random Number Generators를 직접 수락합니다.  
  
 **오버로드된 address\-of 연산자 금지:** C\+\+98\/03에서는 STL 컨테이너 요소가 해당 address\-of 연산자를 오버로드하는 것이 금지되었습니다.`CComPtr`와 같은 도우미 클래스가 이러한 오버로드로부터 STL을 보호하도록 설정하기 위해 `CAdapt`과 같은 클래스가 수행하는 작업입니다.  Visual Studio 2010에서 Visual C\+\+ 개발 중 더 많은 상황에서 오버로드된 address\-of 연산자를 거부하도록 STL이 변경되었습니다. C\+\+11은 오버로드된 address\-of 연산자를 허용하도록 하는 요구 사항을 변경했습니다. C\+\+11 및 Visual Studio 2010의 Visual C\+\+는 연산자 오버로드와 관계없이 개체의 실제 주소를 가져올 수 있는 도우미 함수 `std::addressof()`를 제공합니다.  Visual C\+\+ in Visual Studio 2010을 릴리스하기 전에 "`&elem`"의 발생을 적절한 내구성이 있는 "`std::addressof(elem)`"로 바꾸려고 했습니다.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]가 발전되었으므로 연산자의 주소를 오버로드하는 클래스는 STL을 통해 사용할 수 있어야 합니다.  
  
 **[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]는 여러 방식으로 C\+\+11보다 더 뛰어난 기능을 제공합니다.**  
  
 **SCARY 반복기:** [N2911 "빠르고 작은 프로그램을 위해 제네릭 클래스 내의 종속성 최소화"](http://go.microsoft.com/fwlink/p/?LinkID=235115) 및 [N2980 "SCARY 반복기 할당 및 초기화, 개정 1"](http://go.microsoft.com/fwlink/p/?LinkID=235116)에 설명된 대로 C\+\+11 표준에서 허용되기는 하지만 필수가 아닌 SCARY 반복기가 구현되었습니다.  
  
 **파일 시스템:** [TR2 제안](http://go.microsoft.com/fwlink/p/?LinkID=235117)의 `<filesystem>` 헤더가 추가되었습니다.`recursive_directory_iterator` 및 기타 흥미로운 기능을 제공합니다.  TR2 작업이 중지되기 전에 C\+\+0x 실행 속도가 매우 느렸고 C\+\+11로 변경되고 있었기 때문에 [Boost.Filesystem V2](http://go.microsoft.com/fwlink/p/?LinkID=235118)에서 2006 제안이 파생되었습니다. 나중에 Visual Studio 2015에서 구현된 Boost.Filesystem V3로 발전했습니다.  
  
 또한 최적화가 크게 개선되었습니다\!  모든 컨테이너는 이제 현재 자신의 표현에 따라 최적으로 작습니다.  이는 컨테이너 개체 자신을 가리키며, 가리키는 대상의 콘텐츠를 가리키지 않습니다.  예를 들어, `std::vector`에는 세 가지 원시 포인터가 포함됩니다.  Visual Studio 2010의 Visual C\+\+, x86 릴리스 모드에서 `std::vector`는 16바이트입니다.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]에서는 최적으로 작은 12바이트입니다.  프로그램에 100,000개의 벡터가 있으면 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]를 통해 400,000바이트를 절약할 수 있습니다.  메모리 사용을 줄이면 공간과 시간이 둘 다 절감됩니다.  
  
 이 결과는 `std::allocator` 및 `std::less`는 상태 비저장이므로 비어 있는 할당자 및 비교자를 저장하지 않은 결과입니다.  \(이러한 최적화는 상태를 저장하지 않는 이상 사용자 지정 할당자\/비교 연산자에 사용할 수 있습니다.  물론, 상태 저장 할당자\/비교 연산자의 저장을 방지할 수 없지만 매우 드문 경우입니다.\)  
  
 **[!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]에서는 몇 개의 C\+\+14 라이브러리 기능을 구현했습니다.**  
  
-   `less<>`, `greater<>`, `plus<>`, `multiplies<>` 등의 "투명 연산자 함수"  
  
-   `make_unique<T>(args...)` 및 `make_unique<T[]>(n)`  
  
-   `cbegin()`\/`cend()`, `rbegin()`\/`rend()` 및 `crbegin()`\/`crend()` 비멤버 함수  
  
 \[[이 문서의 내용](#top)\]  
  
## 참고 항목  
 [C\+\+의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [람다 식](../cpp/lambda-expressions-in-cpp.md)   
 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)   
 [Visual C\+\+ 팀 블로그](http://blogs.msdn.com/b/vcblog/)   
 [Visual C\+\+의 새로운 기능](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)   
 [Visual C\+\+ 2015의 주요 변경 내용](../porting/visual-cpp-change-history-2003-20151.md)