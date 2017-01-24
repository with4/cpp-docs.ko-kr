---
title: "방법: 릴리스 빌드 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버깅[C++], 릴리스 빌드"
  - "릴리스 빌드, 디버깅"
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 릴리스 빌드 디버깅
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램의 릴리스 빌드를 디버깅할 수 있습니다.  
  
### 릴리스 빌드를 디버깅하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 노드를 클릭합니다.  **디버깅 정보 형식**을 [C7 호환\(\/Z7\)](../../build/reference/z7-zi-zi-debug-information-format.md) 또는 **프로그램 데이터베이스\(\/Zi\)**로 설정합니다.  
  
3.  **링커**를 확장하고 **일반** 노드를 클릭합니다.  **증분 링크 사용**을 [아니요\(\/INCREMENTAL:NO\)](../../build/reference/incremental-link-incrementally.md)로 설정합니다.  
  
4.  **디버깅** 노드를 선택합니다.  **디버그 정보 생성**을 [예\(\/DEBUG\)](../../build/reference/debug-generate-debug-info.md)로 설정합니다.  
  
5.  **최적화** 노드를 선택합니다.  **참조**를 [\/OPT:REF](../../build/reference/opt-optimizations.md)로 설정하고 **COMDAT 정리 사용**을 [\/OPT:ICF](../../build/reference/opt-optimizations.md)로 설정합니다.  
  
6.  이제 릴리스 빌드 응용 프로그램을 디버깅할 수 있습니다.  문제를 찾으려면 오류가 발생한 부분을 찾을 때까지 코드를 단계별로 실행하거나, Just\-In\-Time 디버깅을 사용하여 올바르지 않은 매개 변수 또는 코드를 확인합니다.  
  
     응용 프로그램이 디버그 빌드에서는 작동하지만 릴리스 빌드에서 작동하지 않으면 소스 코드에서 컴파일러 최적화 중 하나에 결함이 있는 경우일 수 있습니다.  문제를 격리하려면 문제의 원인이 되는 최적화와 파일을 찾을 때까지 각 소스 코드 파일에 대해 선택한 최적화를 비활성화합니다. 이 과정을 지원하기 위해 파일을 두 그룹으로 나누고 한 그룹에서 최적화를 비활성화한 다음, 이 그룹에서 문제가 발생하면 문제 있는 파일이 격리될 때까지 그룹을 계속 나눌 수 있습니다.  
  
     디버그 빌드에서 이와 같은 버그를 노출시키려면 [\/RTC](../../build/reference/rtc-run-time-error-checks.md)를 사용하면 됩니다.  
  
     자세한 내용은 [코드 최적화](../../build/reference/optimizing-your-code.md)을 참조하십시오.  
  
## 참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)