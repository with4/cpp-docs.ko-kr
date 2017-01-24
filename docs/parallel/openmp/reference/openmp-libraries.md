---
title: "OpenMP Libraries | Microsoft Docs"
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
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OpenMP Libraries
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

OpenMP 런타임 라이브러리 Visual C\+\+에서를 하는.lib 파일에 설명 합니다.  
  
 다음 라이브러리 Visual C\+\+ OpenMP 런타임 라이브러리 함수를 포함 합니다.  
  
|OpenMP 런타임 라이브러리|특성|  
|----------------------|--------|  
|VCOMP입니다.LIB|다중 스레드 동적 링크 \(VCOMP에 대 한 가져오기 라이브러리입니다.LIB\)입니다.|  
|VCOMPD입니다.LIB|다중 스레드 동적 링크 \(VCOMPD에 대 한 가져오기 라이브러리입니다.\(디버그\) 뚜껑\)|  
  
 컴파일할 때 \_debug가 정의 되 고 `#include omp.h` VCOMPD 소스 코드에서 있습니다.LIB의 기본 lib이입니다.  그렇지 않으면 VCOMP입니다.LIB은 사용 합니다.  
  
 사용할 수 있는 [\/NODEFAULTLIB\(라이브러리 무시\)](../../../build/reference/nodefaultlib-ignore-libraries.md) 기본 lib를 제거 하 고 원하는 lib에 명시적으로 링크 하도록 합니다.  
  
 OpenMP Dll Visual C\+\+ 재배포 가능 패키지 디렉터리에 있고 Openmp를 사용 하는 응용 프로그램을 배포 해야 합니다.  
  
## 참고 항목  
 [Library Reference](../../../parallel/openmp/reference/openmp-library-reference.md)