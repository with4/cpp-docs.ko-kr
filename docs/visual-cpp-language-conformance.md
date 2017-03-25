---
title: "Visual C++ 언어 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 3/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: da3c2e6ce7247d3e8c9a401bc0a133cb8d46a970
ms.openlocfilehash: a13be4d4d32ab0f0bc3cc7b5972e90c4493d06ff
ms.lasthandoff: 03/15/2017

---
# <a name="visual-c-language-conformance"></a>Visual C++ 언어 규칙 
이 항목에서는 Visual Studio 2017 및 이전 버전의 Visual C++용 컴파일러 기능 및 STL(표준 라이브러리) 기능에 대한 ISO C++03, C++11, C++14 및 초안 C++17 언어 표준 규칙을 요약해서 설명합니다. 각 컴파일러 및 STL 기능 이름은 기능을 설명하는 ISO C++ 표준 제안 문서(게시 시 사용 가능한 경우)에 연결됩니다. [지원됨] 열에는 기능에 대한 지원이 먼저 표시되는 Visual Studio 버전이 나열됩니다.  
  
Visual Studio 2017의 규칙 향상 및 기타 변경 사항에 대한 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md) 및 [Visual Studio 2017의 Visual C++에 대한 새로운 기능 ](what-s-new-for-visual-cpp-in-visual-studio.md)을 참조하세요. 이전 버전의 규칙 변경 내용에 대해서는 [Visual C++ change history](porting/visual-cpp-change-history-2003-2015.md)(Visual C++ 주요 변경 내용) 및 [2003~ 2015 Visual C++ 주요 변경 내용](porting/visual-cpp-what-s-new-2003-through-2015.md)을 참조하세요. C++ 팀의 최신 뉴스를 보려면 [Visual C++ 팀 블로그](http://blogs.msdn.microsoft.com/vcblog/)를 방문하세요.  
  
## <a name="compiler-features"></a>컴파일러 기능  
  
|기능 영역| |  
|----|---|  
|__C++03/11 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;그 밖의 모든 항목|VS 2015 <sup>[1](#note_1)</sup>|
|&nbsp;&nbsp;2단계 이름 조회|아니요|
|&nbsp;&nbsp;[N2634 Expression SFINAE](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|부분 <sup>[2](#note_2)</sup>|
|&nbsp;&nbsp;[N1653 C99 전처리기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|부분 <sup>[3](#note_3)</sup>|
|&nbsp;&nbsp;[N1988 확장된 정수 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|해당 없음 <sup>[4](#note_4)</sup>|
|__C++14 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;[N3664 할당 방지/융합](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3664.html)|해당 없음 <sup><sup>[5](#note_5)</sup></sup>|
|&nbsp;&nbsp;[N3323 컨텍스트 변환에 대해 조정된 표현](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3323.pdf)|VS 2013|
|&nbsp;&nbsp;[N3472 이진 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3472.pdf)|VS 2015|
|&nbsp;&nbsp;[N3638 auto 및 decltype(auto) 반환 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3638.html)|VS 2015|
|&nbsp;&nbsp;[N3648 init 캡처](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3648.html)|VS 2015|
|&nbsp;&nbsp;[N3649 제네릭 람다](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3649.html)|VS 2015|
|&nbsp;&nbsp;[N3651 변수 템플릿](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3651.pdf)|VS 2015.2|
|&nbsp;&nbsp;[N3652 확장된 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)|VS 2017|
|&nbsp;&nbsp;[N3653 집계에 대한 NSDMI](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3653.html)|VS 2017|
|&nbsp;&nbsp;[N3760 [[deprecated]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3760.html)|VS 2015|
|&nbsp;&nbsp;[N3778 크기가 지정된 할당 해제](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3778.html)|VS 2015|
|&nbsp;&nbsp;[N3781 자릿수 구분 기호](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3781.pdf)|VS 2015|
|__C++17 핵심 언어 기능__|__지원됨__|
|&nbsp;&nbsp;[N3922 중괄호로 묶인 Init 목록을 사용한 auto에 대한 새 규칙](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)|VS 2015|
|&nbsp;&nbsp;[N3928 간결한 static_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)|VS 2017 [*](#note_star)|
|&nbsp;&nbsp;[N4051 템플릿 template-parameters의 typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)|VS 2015|
|&nbsp;&nbsp;[N4086 삼중자 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)|VS 2010|
|&nbsp;&nbsp;[N4230 중첩된 네임스페이스 정의](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4230.html)|VS 2015.3 [*](#note_star)|
|&nbsp;&nbsp;[N4261 한정 변환 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4261.html)|아니요|
|&nbsp;&nbsp;[N4266 네임스페이스 및 열거자에 대한 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)|VS 2015|
|&nbsp;&nbsp;[N4267 u8 문자 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)|VS 2015|
|&nbsp;&nbsp;[N4268 더 많은 비형식 템플릿 인수 허용](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4268.html)|아니요|
|&nbsp;&nbsp;[N4295 식 폴딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4295.html)|아니요|
|&nbsp;&nbsp;[P0036R0 일부 비어 있는 단항 폴드 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0036r0.pdf)|아니요|
|&nbsp;&nbsp;[P0001R1 레지스터 키워드 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0002R1 bool 형식 operator++ 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)|아니요|
|&nbsp;&nbsp;[P0012R1 형식 시스템에 noexcept 추가](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0012r1.html)|아니요|
|&nbsp;&nbsp;[P0017R1 확장된 집계 초기화](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)|아니요|
|&nbsp;&nbsp;[P0018R3 값으로 *this 캡처](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0061R1 __has_include](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0061r1.html)|아니요|
|&nbsp;&nbsp;[P0136R1 상속 생성자 다시 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)|아니요|
|&nbsp;&nbsp;[P0138R2 정수에서 고정 열거형 Direct-list-init](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0170R1 constexpr 람다](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0170r1.pdf)|아니요|
|&nbsp;&nbsp;[P0184R0 일반화된 range-based for 루프](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)|VS 2017|
|&nbsp;&nbsp;[P0188R1 [[fallthrough]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r1.pdf)|VS 2017 [*](#note_star)|
|&nbsp;&nbsp;[P0189R1 [[nodiscard]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0189r1.pdf)|아니요|
|&nbsp;&nbsp;[P0212R1 [[maybe_unused]] 특성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0212r1.pdf)|VS 2017.x [*](#note_star)|
|&nbsp;&nbsp;[P0245R1 Hexfloat 리터럴](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0245r1.html)|아니요|
|&nbsp;&nbsp;[P0028R4 반복 없이 특성 네임스페이스 사용](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0028r4.html)|아니요|
|&nbsp;&nbsp;[P0035R4 과다 정렬된 동적 메모리 할당](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0035r4.html)|아니요|
|&nbsp;&nbsp;[P0091R3 클래스 템플릿에 대한 템플릿 인수 추론](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)|아니요|
|&nbsp;&nbsp;[P0127R2 자동으로 비형식 템플릿 매개 변수 선언](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)|아니요|
|&nbsp;&nbsp;[P0135R1 보장된 복사 생략](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0135r1.html)|아니요|
|&nbsp;&nbsp;[P0145R3 식 계산 순서 구체화](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0145r3.pdf)|아니요|
|&nbsp;&nbsp;[P0217R3 구조적 바인딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0217r3.html)|아니요|
|&nbsp;&nbsp;[P0283R2 인식할 수 없는 특성 무시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0283r2.html)|아니요|
|&nbsp;&nbsp;[P0292R2 constexpr if 문](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0292r2.html)|아니요|
|&nbsp;&nbsp;[P0305R1 이니셜라이저를 사용하는 선택 문](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0305r1.html)|아니요|
|&nbsp;&nbsp;[P0386R2 인라인 변수](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0386r2.pdf)|아니요|
|&nbsp;&nbsp;[P0522R0 template-parameters 템플릿을 호환되는 인수와 일치](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0522r0.html)|아니요|
|&nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|아니요|
|&nbsp;&nbsp;[P0195R2 using 선언의 팩 확장](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0195r2.html)|아니요|

## <a name="standard-library--stl-features"></a>표준 라이브러리 / STL 기능

|기능 영역| |
|---|---|
|__C++17 표준 라이브러리 기능__|__지원됨__|
|&nbsp;&nbsp;P0433R2 STL에 대한 추론 가이드|아니요|
|&nbsp;&nbsp;P0607R0 STL에 대한 인라인 변수(옵션 A 및 B2)|아니요|
|&nbsp;&nbsp;[P0258R2 has_unique_object_representations](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0258r2.html)|아니요|
|&nbsp;&nbsp;[P0426R1 char_traits에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html)|아니요|
|&nbsp;&nbsp;P0604R0 is\_callable/result\_of에서 is\_invocable/invoke\_result로 변경(옵션 A 및 B)|아니요|
|&nbsp;&nbsp;P0156R2 Variadic lock\_guard에서 scoped\_lock으로 이름 바꾸기|아니요|
|&nbsp;&nbsp;P0558R1 원자성<T> 이름 지정 기본 클래스 불일치 해결|아니요|
|&nbsp;&nbsp;P0298R3 std::byte|아니요|
|&nbsp;&nbsp;[P0063R3 C11 표준 라이브러리](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)|아니요|
|&nbsp;&nbsp;[P0030R1 hypot(x, y, z)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf)|아니요|
|&nbsp;&nbsp;[P0435R1 common_type 점검](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0435r1.pdf)<br />&nbsp;&nbsp;P0548R1 common\_type 및 기간 조정|아니요|
|&nbsp;&nbsp;[P0513R0 악성 공격 해시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0513r0.pdf)<br />&nbsp;&nbsp;P0599R1 noexcept 해시|아니요|
|&nbsp;&nbsp;[P0033R1 enable_shared_from_this 다시 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html)|아니요|
|&nbsp;&nbsp;[P0220R1 라이브러리 기본 사항 V1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)|부분 <sup>[6](#note_6)</sup>|
|&nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html)<br />&nbsp;&nbsp;[P0497R0 배열에 대한 shared_ptr 해결](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html)|아니요|
|&nbsp;&nbsp;[P0084R2 Emplace 반환 형식](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0084r2.pdf)|아니요|
|&nbsp;&nbsp;[P0083R3 맵 및 집합 스플라이스](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)<br />&nbsp;&nbsp;[P0508R0 명확히 insert_return_type 설명](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html)|아니요|
|&nbsp;&nbsp;[P0031R0 \<array>(다시 실행) 및 \<iterator>에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0031r0.html)|아니요|
|&nbsp;&nbsp;[P0505R0 \<chrono>(다시 실행)에 대한 constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0505r0.html)|아니요|
|&nbsp;&nbsp;[P0005R4 not_fn()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html)<br />&nbsp;&nbsp;[P0358R1 not_fn()에 대한 수정 사항](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html)|아니요|
|&nbsp;&nbsp;[P0295R0 gcd(), lcm()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0295r0.pdf)|아니요|
|&nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size 등](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0154r1.html)|아니요|
|&nbsp;&nbsp;[P0067R5 기본 문자열 변환](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html)|아니요|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: Boyer-Moore search()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 검색자 반환 형식 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0253r1.pdf)|아니요|
|&nbsp;&nbsp;P0618R0 \<codecvt> 사용 중단|아니요|
|&nbsp;&nbsp;[P0521R0 shared_ptr::unique() 사용 중단](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0521r0.html)|아니요|
|&nbsp;&nbsp;[P0174R2 남아 있는 라이브러리 파트 사용 중단](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html)|아니요|
|&nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html)|아니요|
|&nbsp;&nbsp;[P0302R1 std::function에서 할당자 지원 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html)|아니요|
|&nbsp;&nbsp;[P0040R3 메모리 관리 도구 확장](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0040r3.html)|아니요|
|&nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<memory_resource>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4562.html#memory.resource.synop)<br />&nbsp;&nbsp;[P0337R0 polymorphic_allocator 할당 삭제](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0337r0.html)|아니요|
|&nbsp;&nbsp;[P0024R2 병렬 알고리즘](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html)<br />&nbsp;&nbsp;[P0336R1 병렬 실행 정책 이름 바꾸기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0336r1.pdf)<br />&nbsp;&nbsp;[P0394R4 예외가 발생할 경우 병렬 알고리즘을 종료()해야 함](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0394r4.html)<br />&nbsp;&nbsp;P0452R1 \<numeric> 병렬 알고리즘 통합|아니요|
|&nbsp;&nbsp;[P0226R1 수학 특수 함수](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0226r1.pdf)|아니요|
|&nbsp;&nbsp;[P0218R1 \<filesystem>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html)<br />&nbsp;&nbsp;[P0219R1 파일 시스템에 대한 상대 경로](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0219r1.html)<br />&nbsp;&nbsp;[P0392R0 파일 시스템 경로에서 string_view 지원](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0392r0.pdf)<br />&nbsp;&nbsp;P0430R2 Non-POSIX 파일 시스템 지원<br />&nbsp;&nbsp;P0492R2 파일 시스템에 대한 NB 설명 확인|아니요 <sup>[7](#note_7)</sup>|
|&nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0152r1.html)|VS 2017.x|
|&nbsp;&nbsp;[P0403R1 \<string_view>용 UDL("meow"sv 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0403r1.html)|VS 2017.x|
|&nbsp;&nbsp;[P0418R2 atomic compare_exchange memory_order 요구 사항](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0418r2.html)|VS 2017.x|
|&nbsp;&nbsp;[P0516R0 shared_future 복사를 noexcept로 표시](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0516r0.html)|VS 2017.x|
|&nbsp;&nbsp;[P0517R0 future_errc에서 future_error 생성](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0517r0.html)|VS 2017.x|
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
|&nbsp;&nbsp;[N4387 쌍 및 튜플 향상](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4387.html)|VS 2015.2|
|&nbsp;&nbsp;[N4508 shared_mutex(시간 제한 없음)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4508.html)|VS 2015.2|
|&nbsp;&nbsp;[P0004R1 사용되지 않는 Iostreams 별칭 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0004r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0006R0 형식 특성에 대한 변수 템플릿(is_same_v 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0006r0.html)|VS 2015.2|
|&nbsp;&nbsp;[P0007R1 as_const()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0007r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0013R1 논리 연산자 형식 특성(conjunction 등)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0013r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0074R0 owner_less\<>](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0074r0.html)|VS 2015.2|
|&nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0092r1.html)|VS 2015.2|
|&nbsp;&nbsp;[P0156R0 Variadic lock_guard](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0156r0.html)|VS 2015.2|
|&nbsp;&nbsp;[N3911 void_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3911.pdf)|VS 2015|
|&nbsp;&nbsp;[N4089 unique_ptr\<T[]>에서 안전하게 변환](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4089.pdf)|VS 2015|
|&nbsp;&nbsp;[N4169 invoke()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4169.html)|VS 2015|
|&nbsp;&nbsp;[N4190 auto_ptr, random_shuffle() 및 이전 \<functional> 항목 제거](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4190.htm)|VS 2015|
|&nbsp;&nbsp;[N4258 noexcept 정리](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4258.pdf)|VS 2015|
|&nbsp;&nbsp;[N4259 uncaught_exceptions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4259.pdf)|VS 2015|
|&nbsp;&nbsp;[N4277 일반적으로 복사 가능한 reference_wrapper](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4277.html)|VS 2015|
|&nbsp;&nbsp;[N4279 map/unordered_map에 대한 insert_or_assign()/try_emplace()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4279.html)|VS 2015|
|&nbsp;&nbsp;[N4280 size(), empty(), data()](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4280.pdf)|VS 2015|
|&nbsp;&nbsp;[N4366 정확하게 unique_ptr 할당 제약](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4366.html)|VS 2015|
|&nbsp;&nbsp;[N4389 bool_constant](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4389.html)|VS 2015|
|&nbsp;&nbsp;[N4510 vector/list/forward_list에서 불완전한 형식 지원](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4510.html)|VS 2013|
|&nbsp;&nbsp;[N4284 연속 반복기](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4284.html)|N/A|
|&nbsp;&nbsp;[P0175R1 C 라이브러리에 대한 개요](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0175r1.html)|N/A|
|&nbsp;&nbsp;[P0180R2 이후 표준화를 위해 네임스페이스 예약](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0180r2.html)|N/A|
|&nbsp;&nbsp;[P0346R1 \<random> 명명법 조정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0346r1.pdf)|N/A|
|&nbsp;&nbsp;[P0371R1 memory_order_consume 권장 안 함](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0371r1.html)|N/A|
|&nbsp;&nbsp;P0467R2 병렬 알고리즘에 대해 정방향 반복기 요구|N/A|
|&nbsp;&nbsp;[P0502R0 일반적으로 예외가 발생할 경우 병렬 알고리즘을 종료()해야 함](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0502r0.html)|N/A|
|&nbsp;&nbsp;[P0503R0 "리터럴 형식" 라이브러리 사용 수정](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0503r0.html)|N/A|
|&nbsp;&nbsp;[P0509R1 "예외 처리에 대한 제한" 업데이트](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0509r1.pdf)|N/A|
|&nbsp;&nbsp;P0518R1 병렬 알고리즘에서 일반적으로 복사 구성 가능한 요소 복사|N/A|
|&nbsp;&nbsp;P0523R1 병렬 알고리즘의 복잡성 요구 사항 완화(일반)|N/A|
|&nbsp;&nbsp;P0574R1 병렬 알고리즘의 복잡성 요구 사항 완화(특정)|N/A|
|&nbsp;&nbsp;P0623R0 최종 C++17 병렬 알고리즘 수정 사항|N/A|
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
__VS 2017.x__는 Visual Studio 2017의 이후 업데이트에서 지원할 예정인 기능을 나타냅니다.  
  
### <a name="notes"></a>노트  
<a name="note_1"></a>__1__ C++11에서 사용되지 않는 C++03의 동적 예외 사양을 무시합니다. 이러한 사양은 구현할 계획이 없으며 향후 C++ 표준에서 제거할 예정입니다.  
<a name="note_2"></a>__2__ Visual Studio 2015 업데이트 2 이후에는 컴파일러에서 표준 라이브러리에 대한 Expression SFINAE를 충분히 지원하고 있지만 여전히 완전하지는 않습니다.  
<a name="note_3"></a>__3__ Visual Studio 2017에서 C99 전처리기 규칙에 대한 컴파일러의 지원이 완전하지 않습니다. Variadic 매크로는 지원되지만 전처리기의 동작에 많은 버그가 있습니다.  
<a name="note_4"></a>__4__ 확장된 정수 형식에 대한 지원이 컴파일러에서 허용되지만 필수는 아니므로 [적용할 수 없음]으로 표시됩니다.  GCC 및 Clang와 마찬가지로 지원하지 않기로 선택했습니다.  
<a name="note_5"></a>__5__ 마찬가지로 이 최적화 구현이 컴파일러에서 허용되지만 필수는 아니므로 [적용할 수 없음]으로 표시됩니다.  
<a name="note_6"></a>__6__ Visual Studio 2015에서 완전히 구현되지 않은 기능이 이 표에 나와 있습니다.  
<a name="note_7"></a>__7__ 파일 시스템 TS는 기록을 위해 \<experimental/filesystem> 및 \<filesystem> 모두에서 구현되지만 네임스페이스를 이동하기 전에 구현을 수정해야 합니다. 이 작업이 완료될 때까지는 기능이 아직 구현되지 않은 것으로 표시됩니다.  
<a name="note_star"></a>__*__ 이러한 기능은 [/std:c++latest](./build/reference/std-specify-language-standard-version.md) 컴파일러 옵션에 의해 보호됩니다.  
  
## <a name="see-also"></a>참고 항목  
[C++ 언어 참조](cpp/cpp-language-reference.md)  
[C++ 표준 라이브러리](standard-library/cpp-standard-library-reference.md)   
[Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)  
[Visual Studio 2017의 Visual C++에 대한 새로운 기능](what-s-new-for-visual-cpp-in-visual-studio.md)  
[2003~ 2015 Visual C++ 주요 변경 내용](porting/visual-cpp-change-history-2003-2015.md)  
[Visual C++ 2003 ~ 2015의 새로운 기능](porting/visual-cpp-what-s-new-2003-through-2015.md)  
[Visual C++ 팀 블로그](http://blogs.msdn.microsoft.com/vcblog/)  

