---
title: "Visual C++ 언어 규칙 | Microsoft Docs"
ms.date: 11/15/2017
ms.technology:
- cpp-language
ms.topic: article
dev_langs:
- C++
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49aabbcc746470815db40f15fa00774d5e05bfe5
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="visual-c-language-conformance"></a>Visual C++ 언어 규칙

이 항목에서는 Visual Studio 2017 및 이전 버전의 C++ 컴파일러에 대한 컴파일러 기능 및 표준 라이브러리 기능의 ISO C++03, C++11, C++14, C++17 및 초안 C++20 언어 표준 규칙을 요약하고 있습니다. 각 컴파일러 및 표준 라이브러리 기능 이름은 기능을 설명하는 ISO C++ 표준 제안 문서에 연결됩니다(게시 시점에 사용 가능한 경우). [지원됨] 열에는 기능에 대한 지원이 먼저 표시되는 Visual Studio 버전이 나열됩니다.

Visual Studio 2017의 규칙 향상 및 기타 변경 사항에 대한 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md) 및 [Visual Studio 2017의 Visual C++에 대한 새로운 기능 ](what-s-new-for-visual-cpp-in-visual-studio.md)을 참조하세요. 이전 버전의 규칙 변경 내용에 대해서는 [Visual C++ change history](porting/visual-cpp-change-history-2003-2015.md)(Visual C++ 주요 변경 내용) 및 [2003~ 2015 Visual C++ 주요 변경 내용](porting/visual-cpp-what-s-new-2003-through-2015.md)을 참조하세요. C++ 팀의 최신 뉴스를 보려면 [Visual C++ 팀 블로그](https://blogs.msdn.microsoft.com/vcblog/)를 방문하세요.

> [!NOTE]
> Visual Studio 2015 ~ Visual Studio 2017에서 새로운 이진 변경 내용이 없습니다.

## <a name="compiler-features"></a>컴파일러 기능

|기능 영역| |
|----|---|
|__C++03/11 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;그 밖의 모든 항목|VS 2015 <sup>[A](#note_A)</sup>|
|&nbsp;&nbsp;2단계 이름 조회|부분 <sup>[B](#note_B)</sup>|
|&nbsp;&nbsp;[N2634 Expression SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|부분 <sup>[C](#note_C)</sup>|
|&nbsp;&nbsp;[N1653 C99 전처리기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|부분 <sup>[D](#note_D)</sup>|
|&nbsp;&nbsp;[N1988 확장된 정수 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|해당 없음 <sup>[E](#note_E)</sup>|
|__C++14 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;[N3323 컨텍스트 변환에 대해 조정된 표현](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 이진 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 auto 및 decltype(auto) 반환 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init 캡처](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 제네릭 람다](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3760 [[deprecated]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 크기가 지정된 할당 해제](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 자릿수 구분 기호](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|&nbsp;&nbsp;[N3651 변수 템플릿](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 확장된 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017|
|&nbsp;&nbsp;[N3653 집계에 대한 NSDMI](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017|
|&nbsp;&nbsp;[N3664 할당 방지/융합](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html)|해당 없음 <sup>[F](#note_F)</sup>|
|__C++17 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;[N4086 삼중자 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N3922 중괄호로 묶인 Init 목록을 사용한 auto에 대한 새 규칙](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4051 템플릿 template-parameters의 typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4266 네임스페이스 및 열거자에 대한 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4267 u8 문자 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4230 중첩된 네임스페이스 정의](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N3928 간결한 static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0184R0 일반화된 범위 기반 for 루프](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0188R1 [[fallthrough]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0001R1 레지스터 키워드 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0002R1 bool 형식 operator++ 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0018R3 값으로 *this 캡처](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0028R4 반복 없이 특성 네임스페이스 사용](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0061R1 __has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0138R2 정수에서 고정 열거형 Direct-list-init](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0170R1 constexpr 람다](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0189R1 [[nodiscard]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0212R1 [[maybe_unused]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0217R3 구조적 바인딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0292R2 constexpr if 문](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|VS 2017 15.3 <sup>[G](#note_G)</sup>|
|&nbsp;&nbsp;[P0305R1 이니셜라이저를 사용하는 선택 문](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0245R1 Hexfloat 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4268 더 많은 비형식 템플릿 인수 허용](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4295 식 폴딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0012R1 형식 시스템에 noexcept 추가](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0035R4 과다 정렬된 동적 메모리 할당](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0386R2 인라인 변수](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0522R0 template-parameters 템플릿을 호환되는 인수와 일치](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0036R0 일부 비어 있는 단항 폴드 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4261 한정 변환 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|아니요|
|&nbsp;&nbsp;[P0017R1 확장된 집계 초기화](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|아니요|
|&nbsp;&nbsp;[P0091R3 클래스 템플릿에 대한 템플릿 인수 추론](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)<br />&nbsp;&nbsp;[P0512R0 클래스 템플릿 인수 추론 문제(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0512r0.pdf)|아니요|
|&nbsp;&nbsp;[P0127R2 자동으로 비형식 템플릿 매개 변수 선언](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|아니요|
|&nbsp;&nbsp;[P0135R1 보장된 복사 생략](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|아니요 <sup>[H](#note_H)</sup>|
|&nbsp;&nbsp;[P0136R1 상속 생성자 다시 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|아니요|
|&nbsp;&nbsp;[P0145R3 식 계산 순서 구체화](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)<br />&nbsp;&nbsp;[P0400R0 함수 인수 평가 순서(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0400r0.html)|아니요|
|&nbsp;&nbsp;[P0195R2 using 선언의 팩 확장](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|아니요|
|&nbsp;&nbsp;[P0283R2 인식할 수 없는 특성 무시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|아니요|
|&nbsp;&nbsp;[P0702R1 이니셜라이저 목록 작업자(initializer-list actors)에 대한 클래스 템플릿 인수 추론 문제 해결(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0702r1.html)|아니요|
|__C++20 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;[P0306R4 쉼표 생략 및 쉼표 삭제에&#95;&#95;VA_OPT&#95;&#95; 추가(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0306r4.pdf)|아니요|
|&nbsp;&nbsp;[P0329R4 지정된 초기화(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)|아니요|
|&nbsp;&nbsp;[P0409R2 [=, this] 람다 캡처 허용(영문)](http://open-std.org/JTC1/SC22/WG21/docs/papers/2017/p0409r2.html)|아니요|
|&nbsp;&nbsp;[P0428R2 일반 람다에 대한 친숙한 템플릿 구문(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0428r2.pdf)|아니요|
|&nbsp;&nbsp;[P0683R1 비트 필드에 대한 기본 멤버 이니셜라이저(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0683r1.html)|아니요|
|&nbsp;&nbsp;[P0704R1 멤버에 대한 const lvalue ref-qualified 포인터 수정(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0704r1.html)|아니요|
|&nbsp;&nbsp;[P0734R0 개념(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0734r0.pdf)|아니요|


## <a name="standard-library-features"></a>표준 라이브러리 기능

|기능 영역| |
|---|---|
|__C++20 표준 라이브러리 기능__|__지원됨__|
|&nbsp;&nbsp;[P0463R1 endian(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html)|아니요|
|&nbsp;&nbsp;[P0674R1 배열에 대한 make_shared()(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0674r1.html)|아니요|
|__C++17 표준 라이브러리 기능__|__지원됨__|
|&nbsp;&nbsp;[P0433R2 클래스 템플릿에 대한 템플릿 추론을 표준 라이브러리에 통합(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html)<br />&nbsp;&nbsp;[P0739R0 표준 라이브러리에 클래스 템플릿 인수 추론 통합 향상(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html)|아니요|
|&nbsp;&nbsp;[P0426R1 char_traits에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|아니요|
|&nbsp;&nbsp;[P0030R1 hypot(x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|아니요|
|&nbsp;&nbsp;[P0220R1 라이브러리 기본 사항 V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|부분 <sup>[J](#note_J)</sup>|
|&nbsp;&nbsp;[P0067R5 기본 문자열 변환](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|아니요|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<memory_resource>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br />&nbsp;&nbsp;[P0337R0 polymorphic_allocator 할당 삭제](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|아니요|
|&nbsp;&nbsp;[P0024R2 병렬 알고리즘](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br />&nbsp;&nbsp;[P0336R1 병렬 실행 정책 이름 바꾸기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br />&nbsp;&nbsp;[P0394R4 예외가 발생할 경우 병렬 알고리즘을 종료()해야 함](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br />&nbsp;&nbsp;[P0452R1 \<numeric> 병렬 알고리즘 통합(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0452r1.html)|아니요|
|&nbsp;&nbsp;[P0226R1 수학 특수 함수](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|아니요|
|&nbsp;&nbsp;[P0218R1 \<filesystem>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br />&nbsp;&nbsp;[P0219R1 파일 시스템에 대한 상대 경로](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br />&nbsp;&nbsp;[P0317R1 파일 시스템에 대한 디렉터리 항목 캐싱(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p03179r1.html)<br />&nbsp;&nbsp;[P0392R0 파일 시스템 경로에서 string_view 지원](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br />&nbsp;&nbsp;[P0430R2 비POSIX 파일 시스템 지원(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0430r2.pdf)<br />&nbsp;&nbsp;[P0492R2 파일 시스템에 대한 NB 주석 해석(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0492r2.html)|아니요 <sup>[K](#note_K)</sup>|
|&nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br />&nbsp;&nbsp;[P0358R1 not_fn()에 대한 수정 사항](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0033R1 enable_shared_from_this 다시 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0083R3 맵 및 집합 스플라이스](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br />&nbsp;&nbsp;[P0508R0 명확히 insert_return_type 설명](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0174R2 남아 있는 라이브러리 파트 사용 중단](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0302R1 std::function에서 할당자 지원 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br />&nbsp;&nbsp;[P0497R0 배열에 대한 shared_ptr 해결](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0521R0 shared_ptr::unique() 사용 중단](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0607R0 표준 라이브러리에 대한 인라인 변수(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0618R0 \<codecvt> 사용 중단(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0618r0.html)|VS 2017 15.5 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 검색자 반환 형식 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0031R0 \<array>(다시 실행) 및 \<iterator>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0040R3 메모리 관리 도구 확장](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0084R2 Emplace 반환 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size 등](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0156R2 Variadic lock\_guard를 scoped\_lock으로 이름 바꾸기(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r2.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|VS 2017 15.3 <sup>[L](#note_L)</sup>|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0298R3 std::byte(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0298r3.pdf)|VS 2017 15.3 <sup>[17](#note_17), [byte](#note_byte)</sup>|
|&nbsp;&nbsp;[P0403R1 \<string_view>용 UDL("meow"sv 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0418R2 atomic compare_exchange memory_order 요구 사항](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0435R1 common_type 점검](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br />&nbsp;&nbsp;[P0548R1 Tweaking common\_type 및 기간 조정(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0548r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0505R0 \<chrono>(다시 실행)에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[P0513R0 악성 공격 해시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br />&nbsp;&nbsp;[P0599R1 noexcept 해시(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0599r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0516R0 shared_future 복사를 noexcept로 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0517R0 future_errc에서 future_error 생성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0558R1 원자성<T> 이름 지정 기본 클래스 불일치 해결(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0558r1.pdf)|VS 2017 15.3 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0604R0 is\_callable/result\_of를 invoke\_result, is\_invocable, is\_nothrow\_invocable로 변경(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0604r0.html)|VS 2017 15.3 <sup>[17](#note_17)</sup>|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<algorithm> sample()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#alg.random.sample)|VS 2017|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<any>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#any)|VS 2017|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<optional>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#optional)|VS 2017|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<string_view>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#string.view)|VS 2017|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<tuple> apply()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#tuple)|VS 2017|
|&nbsp;&nbsp;[P0032R3 variant/any/optional에 대한 동종 인터페이스](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0032r3.pdf)|VS 2017|
|&nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0077r2.html)|VS 2017|
|&nbsp;&nbsp;[P0088R3 \<variant>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0088r3.html)|VS 2017|
|&nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0163r0.html)|VS 2017|
|&nbsp;&nbsp;[P0209R2 make_from_tuple()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0209r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0254R2 string_view 및 std::string 통합](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0254r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0307R2 선택적으로 크거나 같게 만들기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0307r2.pdf)|VS 2017|
|&nbsp;&nbsp;[P0393R3 Variant를 크거나 같게 만들기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0393r3.html)|VS 2017|
|&nbsp;&nbsp;[P0504R0 in_place_t/in_place_type_t\<T>/in_place_index_t\<I> 다시 방문](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0504r0.html)|VS 2017|
|&nbsp;&nbsp;[P0510R0 없음, 배열, 참조, 불완전한 형식의 variant 거부](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0510r0.html)|VS 2017|
|&nbsp;&nbsp;[P0025R1 clamp()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0025r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0185r1.html)|VS 2015.3|
|&nbsp;&nbsp;[P0272R1 상수가 아닌 basic_string::data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0272r1.html)|VS 2015.3|
|&nbsp;&nbsp;[N4387 쌍 및 튜플 향상](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4508 shared_mutex(시간 제한 없음)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0004R1 사용되지 않는 Iostreams 별칭 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2 <sup>[rem](#note_rem)</sup>|
|&nbsp;&nbsp;[P0006R0 형식 특성에 대한 변수 템플릿(is_same_v 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0013R1 논리 연산자 형식 특성(conjunction 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0156R0 Variadic lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4089 unique_ptr\<T[]>에서 안전하게 변환](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4169 invoke()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4190 auto_ptr, random_shuffle() 및 이전 \<functional> 항목 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015 <sup>[rem](#note_rem)</sup>|
|&nbsp;&nbsp;[N4258 noexcept 정리](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4259 uncaught_exceptions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4277 일반적으로 복사 가능한 reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4279 map/unordered_map에 대한 insert_or_assign()/try_emplace()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4280 size(), empty(), data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4366 정확하게 unique_ptr 할당 제약](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015 <sup>[14](#note_14)</sup>|
|&nbsp;&nbsp;[P0063R3 C11 표준 라이브러리](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup>|
|&nbsp;&nbsp;[N4510 vector/list/forward_list에서 불완전한 형식 지원](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013 <sup>[14](#note_14)</sup>|
|__C++14 표준 라이브러리 기능__|__지원됨__|
|&nbsp;&nbsp;[N3462 SFINAE-Friendly result_of](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3462.html)|VS 2015.2|
|&nbsp;&nbsp;[N3302 \<complex>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3302.html)|VS 2015|
|&nbsp;&nbsp;[N3469 \<chrono>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3469.html)|VS 2015|
|&nbsp;&nbsp;[N3470 \<array>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3470.html)|VS 2015|
|&nbsp;&nbsp;[N3471 \<initializer_list>, \<tuple>, \<utility>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3471.html)|VS 2015|
|&nbsp;&nbsp;[N3545 integral_constant::operator()()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3545.pdf)|VS 2015|
|&nbsp;&nbsp;[N3642 \<chrono>, \<string>에 대한 UDL(1729ms, "meow" 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3642.pdf)|VS 2015|
|&nbsp;&nbsp;[N3644 Null 정방향 반복기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3644.pdf)|VS 2015|
|&nbsp;&nbsp;[N3654 quoted()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3654.html)|VS 2015|
|&nbsp;&nbsp;[N3657 유형이 다른 연관 조회](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3657.htm)|VS 2015|
|&nbsp;&nbsp;[N3658 integer_sequence](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3658.html)|VS 2015|
|&nbsp;&nbsp;[N3659 shared_mutex(시간 제한)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3659.html)|VS 2015|
|&nbsp;&nbsp;[N3668 exchange()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3668.html)|VS 2015|
|&nbsp;&nbsp;[N3669 const 없는 constexpr 멤버 함수 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3669.pdf)|VS 2015|
|&nbsp;&nbsp;[N3670 get\<T>()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3670.html)|VS 2015|
|&nbsp;&nbsp;[N3671 이중 범위 equal(), is_permutation(), mismatch()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3671.html)|VS 2015|
|&nbsp;&nbsp;[N3778 크기가 지정된 할당 해제](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3779 \<complex>에 대한 UDL(3.14i 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3779.pdf)|VS 2015|
|&nbsp;&nbsp;[N3789 \<functional>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3789.htm)|VS 2015|
|&nbsp;&nbsp;[N3887 tuple_element_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3887.pdf)|VS 2015|
|&nbsp;&nbsp;[N3891 shared_mutex(시간 제한)의 이름을 shared_timed_mutex로 바꾸기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3891.htm)|VS 2015|
|&nbsp;&nbsp;[N3346 최소 컨테이너 요소 요구 사항](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3346.pdf)|VS 2013|
|&nbsp;&nbsp;[N3421 투명 연산자 함수(less\<> 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3421.htm)|VS 2013|
|&nbsp;&nbsp;[N3655 \<type_traits>에 대한 별칭 템플릿(decay_t 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3655.pdf)|VS 2013|
|&nbsp;&nbsp;[N3656 make_unique()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3656.htm)|VS 2013|
|&nbsp;&nbsp;[N3924 rand() 권장 안 함](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3924.pdf)|N/A|

함께 나열된 문서 그룹은 기능이 표준으로 선출되고 해당 기능을 개선하거나 확장하기 위한 문서도 하나 이상 선출되었음을 나타냅니다. 이러한 기능은 함께 구현됩니다.

### <a name="supported-values"></a>지원되는 값

__아니요__는 아직 구현되지 않은 것을 의미합니다.  
__부분__은 Visual Studio 2017에서 부분적으로 구현되었음을 의미합니다. 자세한 내용은 참고 섹션을 참조하세요.  
__해당 없음__은 제안 문서에서 해당 기능을 설명하지 않음을 의미합니다. 이러한 문서에서는 표준 언어를 변경했지만 구현자를 위한 작업을 만들지 않았습니다. 이 기능은 목록의 완전성을 위해 표시됩니다.  
__VS 2010__은 Visual Studio 2010에서 지원되는 기능을 나타냅니다.  
__VS 2013__은 Visual Studio 2013에서 지원되는 기능을 나타냅니다.  
__VS 2015__은 Visual Studio 2015 RTM에서 지원되는 기능을 나타냅니다.  
__VS 2015.2__ 및 __VS 2015.3__은 각각 Visual Studio 2015 업데이트 2와 Visual Studio 2015 업데이트 3에서 지원되는 기능을 나타냅니다.  
__VS 2017__은 Visual Studio 2017 RTM에서 지원되는 기능을 나타냅니다.  
__VS 2017 15.3__은 Visual Studio 2017 버전 15.3에서 지원되는 기능을 나타냅니다.  
__VS 2017 15.5__는 Visual Studio 2017 버전 15.5에서 지원되는 기능을 나타냅니다.

### <a name="notes"></a>노트

<a name="note_A"></a>__A__ C++11에서 사용되지 않는 C++03의 동적 예외 사양을 무시합니다. 이러한 사양은 구현할 계획이 없으며 향후 C++ 표준에서 제거할 예정입니다.  
<a name="note_B"></a>__B__ 2단계 이름 조회에 대한 컴파일러의 지원은 향상되었지만 여전히 불완전합니다.  
<a name="note_C"></a>__C__ Expression SFINAE에 대한 컴파일러의 지원은 Visual Studio 2015 업데이트 2 이후로 표준 라이브러리에는 충분했지만 지원은 여전히 불완전합니다.  
<a name="note_D"></a>__D__ Visual Studio 2017에서는 C99 전처리기 규칙에 대한 컴파일러의 지원이 불완전합니다. Variadic 매크로는 지원되지만 전처리기의 동작에 많은 버그가 있습니다.  
<a name="note_E"></a>__E__ 컴파일러에서 확장된 정수 형식을 지원할 수는 있지만 필수는 아니므로 [적용할 수 없음]으로 표시됩니다.  GCC 및 Clang와 마찬가지로 지원하지 않기로 선택했습니다.  
<a name="note_F"></a>__F__ 마찬가지로 컴파일러에서 이 최적화를 구현할 수는 있지만 필수는 아니므로 [적용할 수 없음]으로 표시됩니다.  
<a name="note_G"></a>__G__ [/std:c++14](./build/reference/std-specify-language-standard-version.md) 아래에서 억제 가능한 경고로 표시됩니다.  
<a name="note_H"></a>__H__ 이 기능은 Visual Studio 2017 버전 15.3의 미리 보기에서 사용할 수 있었지만, 버그가 발견되어 릴리스에서 제거되었습니다.  
<a name="note_J"></a>__J__ Visual Studio 2015에서 완전하지 않은 기능은 이 표의 다른 곳에 나와 있습니다.  
<a name="note_K"></a>__K__ TS 파일 시스템은 기록을 위해 \<experimental/filesystem> 및 \<filesystem> 모두에서 구현되지만, 네임스페이스를 이동하기 전에 해당 구현을 수정해야 합니다. 이 작업이 완료될 때까지는 기능이 아직 구현되지 않은 것으로 표시됩니다.  
<a name="note_L"></a>__L__ 컴파일러 내장 함수에서 지원됩니다. 이 내장 함수는 아직 Clang에서 사용할 수 없습니다. 이 기능은 사용할 수 있지만 Intellisense에는 아직 사용할 수 없습니다.   
<a name="note_14"></a>__14__ 이러한 C++17 기능은 [/std:c++14](./build/reference/std-specify-language-standard-version.md)(기본값)를 지정한 경우에도 항상 활성화됩니다. 이는 **/std** 옵션을 도입하기 전에 기능이 구현되었거나 조건부 구현이 바람직하지 않게 복잡했기 때문입니다.  
<a name="note_17"></a>__17__ 이러한 기능은 [/std:c++17](./build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](./build/reference/std-specify-language-standard-version.md)) 컴파일러 옵션으로 활성화됩니다.  
<a name="note_byte"></a>__byte__ `std::byte`는 [/std:c++17](./build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](./build/reference/std-specify-language-standard-version.md))로 활성화되지만, 경우에 따라 Windows SDK 헤더와 충돌할 수 있으므로 세분화된 옵트아웃 매크로가 있습니다. `_HAS_STD_BYTE`를 `0`으로 정의하여 비활성화할 수 있습니다.  
<a name="note_C11"></a>__C11__ 유니버셜 CRT에서는 C99 `strftime()` E/O 대체 변환 지정자, C11 `fopen()` 단독 모드 및 C11 `aligned_alloc()`을 제외하고는 C++17에 필요한 C11 표준 라이브러리의 일부를 구현했습니다. 후자는 C11에서 `free()`의 Microsoft 구현과 호환되지 않는 방식으로 `free()`에서 고도로 정렬된 할당을 처리할 수 있어야 하는 `aligned_alloc()`을 지정했기 때문에 구현되지 않을 것입니다.  
<a name="note_rem"></a>__rem__ [/std:c++17](./build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](./build/reference/std-specify-language-standard-version.md)) 컴파일러 옵션이 지정되면 기능이 제거됩니다. 이러한 기능에는 `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS` 및 `_HAS_UNEXPECTED` 옵트아웃 매크로가 있습니다.
  
## <a name="see-also"></a>참고 항목

[C++ 언어 참조](cpp/cpp-language-reference.md)  
[C++ 표준 라이브러리](standard-library/cpp-standard-library-reference.md)   
[Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)  
[Visual Studio 2017의 Visual C++에 대한 새로운 기능](what-s-new-for-visual-cpp-in-visual-studio.md)  
[2003~ 2015 Visual C++ 주요 변경 내용](porting/visual-cpp-change-history-2003-2015.md)  
[Visual C++ 2003 ~ 2015의 새로운 기능](porting/visual-cpp-what-s-new-2003-through-2015.md)  
[Visual C++ 팀 블로그](https://blogs.msdn.microsoft.com/vcblog/)  
