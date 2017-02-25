---
title: "릴리스 빌드를 만들 때의 일반적인 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버그 빌드, 릴리스 빌드의 차이점"
  - "디버그 메모리 할당자"
  - "디버깅[MFC], 릴리스 빌드"
  - "힙 레이아웃 문제"
  - "메모리[C++], 덮어쓰기"
  - "MFC[C++], 릴리스 빌드"
  - "최적화[C++], 컴파일러"
  - "포인터, 스트레이"
  - "프로젝트[C++], 디버그 구성"
  - "릴리스 빌드, 응용 프로그램 빌드"
  - "릴리스 빌드, 문제 해결"
  - "스트레이 포인터"
  - "릴리스 빌드 문제 해결"
  - "Visual C++ 문제 해결"
  - "예기치 않은 코드 생성"
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 릴리스 빌드를 만들 때의 일반적인 문제
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개발하는 동안 대개 프로젝트의 디버그 빌드를 빌드하여 테스트하게 됩니다.  그런 다음 릴리스 빌드용 응용 프로그램을 빌드하면 액세스 위반이 생길 수 있습니다.  
  
 아래 목록에서는 디버그 빌드와 릴리스\(비디버그\) 빌드의 기본적인 차이점을 보여 줍니다.  이 외에도 차이점은 있지만, 응용 프로그램이 디버그 빌드에서는 작동하면서 릴리스 빌드에서는 작동하지 않는 기본적인 차이점은 다음과 같습니다.  
  
-   [힙 레이아웃](#_core_heap_layout)  
  
-   [컴파일](#_core_compilation)  
  
-   [포인터 지원](#_core_pointer_support)  
  
-   [최적화](#_core_optimizations)  
  
 디버그 빌드에서 릴리스 빌드 오류를 찾아내는 방법에 대한 자세한 내용은 컴파일러 옵션 [\/GZ\(디버그 빌드에서 릴리스 빌드 오류 Catch\)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)를 참조하십시오.  
  
##  <a name="_core_heap_layout"></a> 힙 레이아웃  
 응용 프로그램이 디버그 빌드에서는 작동했는데 릴리스 빌드에서는 작동하지 않는 경우의 명백한 문제 중 약 90%는 힙 레이아웃이 원인입니다.  
  
 프로젝트를 디버그용으로 빌드할 때는 디버그 메모리 할당자를 사용합니다.  따라서 할당된 모든 메모리 주위에는 보호 바이트가 놓이게 됩니다.  이 보호 바이트는 메모리 덮어쓰기를 감지합니다.  릴리스 버전과 디버그 버전의 힙 레이아웃은 서로 다르기 때문에, 디버그 빌드에서는 메모리 덮어쓰기로 인한 문제가 발생하지 않아도 릴리스 빌드에서는 심각한 결과를 가져올 수 있습니다.  
  
 자세한 내용은 [메모리 덮어쓰기 확인](../../build/reference/checking-for-memory-overwrites.md) 및 [디버그 빌드를 사용한 메모리 덮어쓰기 확인](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)을 참조하십시오.  
  
##  <a name="_core_compilation"></a> 컴파일  
 릴리스용으로 빌드할 때는 MFC 매크로와 MFC 구현의 많은 부분이 변경됩니다.  특히, ASSERT 매크로는 릴리스 빌드에서 아무 것도 아닌 것으로 평가되므로 ASSERT에 있는 어떤 코드도 실행되지 않습니다.  자세한 내용은 [ASSERT 문 검사](../../build/reference/using-verify-instead-of-assert.md)를 확인하십시오.  
  
 릴리스 빌드에서는 속도 향상을 위해 일부 함수가 인라인되며,  일반적으로 최적화가 설정되어 있습니다.  또한 다른 메모리 할당자가 사용됩니다.  
  
##  <a name="_core_pointer_support"></a> 포인터 지원  
 디버깅 정보가 부족하면 응용 프로그램에서 패딩을 제거합니다.  릴리스 빌드에서는 스트레이 포인터가 디버그 정보를 가리키는 대신 초기화되지 않은 메모리를 가리킬 가능성이 더 큽니다.  
  
##  <a name="_core_optimizations"></a> 최적화  
 코드에 있는 일부 세그먼트의 특성에 따라 최적화 컴파일러가 예기치 않은 코드를 생성하게 될 수 있습니다.  이것이 릴리스 빌드 문제의 원인일 가능성은 가장 적지만 경우에 따라서는 이로 인해 문제가 발생하기도 합니다.  이 문제에 대한 해결책은 [코드 최적화](../../build/reference/optimizing-your-code.md)를 참조하십시오.  
  
## 참고 항목  
 [릴리스 빌드](../../build/reference/release-builds.md)   
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)