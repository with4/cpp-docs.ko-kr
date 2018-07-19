---
title: 릴리스 빌드를 만들 때의 일반적인 문제 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8860783a2cf9fb88b28e24e0bc16eb16c0dd5d77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373168"
---
# <a name="common-problems-when-creating-a-release-build"></a>릴리스 빌드를 만들 때의 일반적인 문제
개발 하는 동안 일반적으로 빌드하고 프로젝트의 디버그 빌드를 테스트 합니다. 다음 릴리스 빌드에 대 한 응용 프로그램을 작성 하는 경우 액세스 위반이 발생할 수 있습니다.  
  
 아래 목록은 디버그 및 릴리스 (비디버그) 빌드 간의 주요 차이점입니다. 다른 차이점으로, 있지만 다음 디버그 빌드에서 작동할 경우 릴리스 빌드에서 응용 프로그램 실패를 발생 시키는 가장 큰 차이점은 있습니다.  
  
-   [힙 레이아웃](#_core_heap_layout)  
  
-   [컴파일](#_core_compilation)  
  
-   [포인터 지원](#_core_pointer_support)  
  
-   [최적화](#_core_optimizations)  
  
 참조는 [/GZ (Catch 릴리스 빌드 디버그 빌드)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) 릴리스를 catch 하는 방법에 대 한 내용은 컴파일러 옵션 빌드 디버그 빌드에서 오류가 발생 합니다.  
  
##  <a name="_core_heap_layout"></a> 힙 레이아웃  
 힙 레이아웃 릴리스가 아닌 디버그에서 응용 프로그램이 작동 하는 경우 명백한 문제 중 약 90 %의 원인이 됩니다.  
  
 디버그에 대 한 프로젝트를 빌드할 때 디버그 메모리 할당자를 사용 하 고 있습니다. 즉, 모든 메모리 할당을 양 끝에 놓이며 보호 바이트입니다. 이러한 보호 바이트 메모리 덮어쓰기를 검색 합니다. 힙 레이아웃 릴리스 및 디버그 간에 서로 다르기 때문에 버전에서 메모리 덮어쓰기 디버그 빌드에서 문제를 만들 수는 있지만 릴리스 빌드 치명적인 영향을 줄 수 있습니다.  
  
 자세한 내용은 참조 [메모리 덮어쓰기 확인](../../build/reference/checking-for-memory-overwrites.md) 및 [디버그 빌드를 확인을 통해을 사용 하 여 메모리 덮어쓰기](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)합니다.  
  
##  <a name="_core_compilation"></a> 컴파일  
 대부분의 MFC 매크로 및 대부분의 릴리스에 대 한 빌드할 때 MFC 구현 변경 합니다. 특히, ASSERT 매크로 릴리스 빌드에서 nothing으로 평가 되므로 어떤 Assert에 코드 실행 되지 것입니다. 자세한 내용은 참조 [ASSERT 문 검사](../../build/reference/using-verify-instead-of-assert.md)합니다.  
  
 일부 함수는 릴리스 빌드에서 속도 향상된을 위해 인라인 처리할 수 없습니다. 일반적으로 릴리스 빌드에서 최적화 켜져 있습니다. 또한 다른 메모리 할당자를 사용 중입니다.  
  
##  <a name="_core_pointer_support"></a> 포인터 지원  
 응용 프로그램에서 안쪽 여백을 제거 하는 디버깅 정보가 부족 합니다. 릴리스 빌드 스트레이 포인터 디버그 정보를 가리키는 대신 초기화 되지 않은 메모리를 가리키는의 가능성이 더를 갖고 있습니다.  
  
##  <a name="_core_optimizations"></a> 최적화  
 코드의 특정 세그먼트의 특성에 따라 최적화 컴파일러 예기치 않은 코드를 생성할 수 있습니다. 릴리스 빌드 문제는 가장 일반적인 원인은 이지만 경우에 따라 발생지 않습니다. 솔루션을 참조 하십시오. [코드 최적화](../../build/reference/optimizing-your-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [릴리스 빌드](../../build/reference/release-builds.md)   
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)