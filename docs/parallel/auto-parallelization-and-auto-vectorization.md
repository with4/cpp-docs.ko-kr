---
title: 자동 병렬화 및 자동 벡터화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1ec19065647f78b4d9b2665003c0aa3a2795ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688468"
---
# <a name="auto-parallelization-and-auto-vectorization"></a>자동 병렬화 및 자동 벡터화
자동 평행화 도우미 및 자동 벡터화 도우미는 코드의 루프 성능을 자동으로 향상시키기 위해 설계되었습니다.  
  
## <a name="auto-parallelizer"></a>자동 평행화 도우미  
 [/Qpar](../build/reference/qpar-auto-parallelizer.md) 컴파일러 스위치를 사용 하면 *자동 병렬화* 코드에서 루프의 합니다. 기존 코드를 변경하지 않고 이 플래그를 지정하면 컴파일러는 코드를 평가하여 평행화에서 이점을 얻을 수 있는 루프를 찾습니다. 많은 작업을 수행하지 않아 평행화의 이점을 얻지 못하는 루프가 있을 수 있고 불필요한 모든 평행화가 스레드 풀 생성, 추가 동기화 또는 성능 향상보다는 성능을 저하시키는 기타 처리를 발생시킬 수 있으므로 컴파일러는 평행화할 루프를 선택하는 데 다소 신중합니다. 예를 들어 루프의 상한값이 컴파일 타임에 알려지지 않은 다음 예를 고려할 수 있습니다.  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 `u`는 작은 값이 될 수 있으므로 컴파일러는 이 루프를 자동으로 평행화하지는 않습니다. 그러나 `u`가 항상 큰 값이 되는 것을 아는 경우 사용자는 이를 평행화하려 할 수 있습니다. 자동 병렬화를 사용 하려면 지정 [#pragma loop(hint_parallel(n))](../preprocessor/loop.md)여기서 `n` 평행 스레드 수입니다. 다음 예에서 컴파일러는 8개 스레드에 걸쳐 루프를 평행화하려고 합니다.  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 모든와 마찬가지로 [pragma 지시문](../preprocessor/pragma-directives-and-the-pragma-keyword.md), 대체 pragma 구문 `__pragma(loop(hint_parallel(n)))` 도 지원 합니다.  
  
 사용자가 원하더라도 컴파일러가 평행화할 수 없는 루프도 있습니다. 예를 들면 다음과 같습니다.  
  
```cpp  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 `upper_bound()` 함수는 호출될 때마다 변경될 수 있습니다. 상한값을 알 수 없으므로 컴파일러는 이 루프를 평행화할 수 없는 이유를 설명하는 진단 메시지를 내보낼 수 있습니다. 다음 예에서는 평행화할 수 있는 루프, 평행화할 수 없는 루프, 명령 프롬프트에서 사용할 컴파일러 구문 및 각 명령줄 옵션에 대한 컴파일러 구문을 보여 줍니다.  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 다음 명령어를 사용하여 컴파일 시:  
  
 **cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-: 1**  
  
 출력 결과:  
  
 **----함수를 분석 하는 중: __cdecl test(void) void**   
 **d:\myproject\mytest.cpp(4): 루프가 병렬화**  
  
 다음 명령어를 사용하여 컴파일 시:  
  
 **cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-: 2**  
  
 출력 결과:  
  
 **----함수를 분석 하는 중: __cdecl test(void) void**   
 **d:\myproject\mytest.cpp(4): 루프가 병렬화**   
 **d:\myproject\mytest.cpp(4): '1008' 이유로 인해 평행 화 되지 않은 루프**  
  
 두 개의 다른 간의 차이 출력에 [/Qpar-report (자동 평행 화 도우미 보고 수준)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) 옵션입니다. **/Qpar-: 1** 공적으로 평행 화 된 루프에 대해서만 평행 화 도우미 메시지를 출력 합니다. **/Qpar-: 2** 모두 성공 하거나 실패 한 루프 평행 화 둘에 대 한 평행 화 도우미 메시지를 출력 합니다.  
  
 이유 코드 및 메시지에 대 한 자세한 내용은 참조 [벡터화 도우미 및 병렬화 도우미 메시지](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)합니다.  
  
## <a name="auto-vectorizer"></a>자동 벡터화 도우미  
 자동 벡터화 도우미는 코드의 루프를 분석하고 가능한 경우 대상 컴퓨터에서 벡터 레지스터 및 명령을 사용하여 루프를 실행합니다. 이를 통해 코드 성능을 향상시킬 수 있습니다. Intel 또는 AMD 프로세서의 SSE2, AVX 및 AVX2 명령 또는 ARM 프로세서의 NEON 명령을 대상으로 하는 컴파일러에 따라는 [/arch](../build/reference/arch-minimum-cpu-architecture.md) 전환 합니다.  
  
 자동 벡터화에 지정한 것 보다과 다른 명령을 생성할 수 있습니다는 **/arch** 전환 합니다. 이러한 명령은 런타임 검사를 통해 코드가 제대로 실행되는지 확인됩니다. 예를 들어 컴파일하는 경우 **/arch: sse2**, SSE4.2 명령을 내보낼 수 있습니다. 런타임 검사는 대상 프로세서에서 SSE4.2를 사용할 수 있는지 확인한 후 프로세서가 해당 명령을 지원하지 않을 경우 비 SSE4.2 버전의 루프로 건너뜁니다.  
  
 기본적으로 자동 벡터화 도우미는 사용할 수 있게 설정되어 있습니다. 벡터화 상태에서 코드의 성능을 비교 하려는 경우 사용할 수 있습니다 [#pragma loop (no_vector)](../preprocessor/loop.md) 에 지정된 된 루프의 벡터화를 사용 하지 않도록 설정 합니다.  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 모든와 마찬가지로 [pragma 지시문](../preprocessor/pragma-directives-and-the-pragma-keyword.md), 대체 pragma 구문 `__pragma(loop(no_vector))` 도 지원 합니다.  
  
 지정할 수는 자동 평행 화 하는 대로 [/Qvec-report (자동 벡터화 도우미 보고 수준)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) 명령줄 옵션 중 하나를 성공적으로 보고 하기 위해 벡터화 된 루프만-**/Qvec-: 1**-또는 성공적으로 및 실패 한 루프를 벡터화-**/Qvec-: 2**).  
  
 이유 코드 및 메시지에 대 한 자세한 내용은 참조 [벡터화 도우미 및 병렬화 도우미 메시지](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)합니다.  
  
 실제로 벡터화 도우미가 작동 하는 방법을 보여 주는 예제를 참조 하십시오. [프로젝트 Austin 2 / 6 부: 페이지 컬링](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [루프](../preprocessor/loop.md)   
 [네이티브 코드의 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/?linkid=263662)   
 [/Qpar (자동 평행 화 도우미)](../build/reference/qpar-auto-parallelizer.md)   
 [/Qpar-report (자동 평행 화 도우미 보고 수준)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/Qvec-report (자동 벡터화 도우미 보고 수준)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [벡터화 도우미 및 평행화 도우미 메시지](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)