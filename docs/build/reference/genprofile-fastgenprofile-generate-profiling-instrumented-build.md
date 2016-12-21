---
title: "/GENPROFILE, /FASTGENPROFILE(계측된 빌드 프로파일링 생성) | Microsoft Docs"
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
  - "GENPROFILE"
  - "FASTGENPROFILE"
  - "/GENPROFILE"
  - "/FASTGENPROFILE"
helpviewer_keywords: 
  - "GENPROFILE"
  - "FASTGENPROFILE"
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GENPROFILE, /FASTGENPROFILE(계측된 빌드 프로파일링 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커에서 PGO\(프로필 기반 최적화\)를 지원하기 위한 .pgd 파일의 생성을 지정합니다.  \/GENPROFILE 및 \/FASTGENPROFILE은 서로 다른 기본 매개 변수를 사용합니다. 프로파일링 중 속도 및 메모리 사용보다 정밀도를 우선하려면 \/GENPROFILE을 사용합니다. 정밀도보다 더 작은 메모리 사용 및 속도를 우선하려면 \/FASTGENPROFILE을 사용합니다.  
  
## 구문  
  
```  
/{GENPROFILE|FASTGENPROFILE}[:{COUNTER32|COUNTER64|EXACT|MEMMAX=#|MEMMIN=#|NOEXACT|NOPATH|NOTRACKEH|PATH|PGD=filename|TRACKEH}]   
```  
  
## 설명  
 COUNTER32 &#124; COUNTER64  
 32비트 프로브 카운터를 지정하려면 COUNTER32를 사용하고, 64비트 프로브 카운터를 지정하려면 COUNTER64를 사용합니다. \/GENPROFILE을 지정하면 기본값은 COUNTER64입니다. \/FASTGENPROFILE을 지정하면 기본값은 COUNTER32입니다.  
  
 EXACT &#124; NOEXACT  
 프로브에 대해 스레드로부터 안전한 연관 증분을 지정하려면 EXACT를 사용합니다. NOEXACT는 프로브에 대해 보호되지 않는 증분 작업을 지정합니다. 기본값은 NOEXACT입니다.  
  
 MEMMAX\=값, MEMMIN\=값  
 메모리의 학습 데이터에 대해 최대 및 최소 예약 크기를 지정하려면 MEMMAX 및 MEMMIN을 사용합니다. 값은 예약할 메모리의 크기\(바이트\)입니다.  기본적으로 이러한 값은 내부 추론에 의해 결정됩니다.  
  
 PATH &#124; NOPATH  
 고유한 각 함수 경로에 대해 별도의 PGO 카운터 집합을 지정하려면 PATH를 사용합니다. 각 함수에 대해 하나의 카운트 집합만 지정하려면 NOPATH를 사용합니다.   \/GENPROFILE을 지정하면 기본값은 PATH입니다. \/FASTGENPROFILE을 지정하면 기본값은 NOPATH입니다.  
  
 TRACKEH &#124; NOTRACKEH  
 학습 중 예외가 throw되면 정확한 개수를 유지하기 위해 추가 카운터를 사용할지 여부를 지정합니다. 정확한 개수를 위해 추가 카운터를 지정하려면 TRACKEH를 사용합니다. 예외 처리를 사용하지 않거나 학습 시나리오에서 예외가 발생하지 않는 코드에 대해 단일 카운터를 지정하려면 NOTRACKEH를 사용합니다.  \/GENPROFILE을 지정하면 기본값은 TRACKEH입니다. \/FASTGENPROFILE을 지정하면 기본값은 NOTRACKEH입니다.  
  
 PGD\=파일 이름  
 .pgd 파일의 기본 파일 이름을 지정합니다. 기본적으로 링커는.pgd 확장명을 가진 기본 실행 가능 이미지 파일 이름을 사용합니다.  
  
 \/GENPROFILE 및 \/FASTGENPROFILE 옵션은 PGO\(프로필 기반 최적화\)를 위한 학습 응용 프로그램을 지원하는 데 필요한 프로파일링 계측 파일을 생성하도록 링커에 지시합니다. 학습 응용 프로그램에 의해 생성된 프로파일링 정보는 빌드 중 전체 대상 프로그램 최적화를 수행하기 위한 입력으로 사용됩니다.   앱 학습 및 빌드 중 성능을 위해 다양한 프로파일링 기능을 제어하는 추가 옵션을 설정할 수 있습니다. \/GENPROFILE에 지정된 기본 옵션은 특히 크고 복잡한 다중 스레드 앱에 대해 가장 정확한 결과를 제공합니다. \/FASTGENPROFILE 옵션은 다른 기본값을 사용하여 학습 중 메모리 사용 공간은 줄고 성능은 향상되지만 정밀도는 저하됩니다.  
  
 프로파일링 정보는 \/FASTGENPROFILE의 \/GENPROFILE을 사용하여 빌드한 후 계측된 앱을 실행할 때 캡처됩니다. 이 정보는 링커에서 \/USEPROFILE 옵션을 지정할 때 사용됩니다. 앱을 학습하는 방법에 대한 자세한 내용 및 수집된 데이터에 대한 세부 정보는 프로필 기반 최적화를 참조하세요.  
  
 \/GENPROFILE 또는 \/FASTGENPROFILE을 지정할 때는 \/LTCG도 지정해야 합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md)