---
title: "링커의 지연 로드된 DLL 지원 | Microsoft Docs"
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
  - "지연 DLL 로드, 링커 지원"
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커의 지연 로드된 DLL 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 링커는 현재 DLL의 지연 로드를 지원합니다.  이 기능을 사용하면 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] 함수 **LoadLibrary** 및 **GetProcAddress**를 사용하여 지연 로드하는 DLL을 구현할 필요가 없습니다.  
  
 Visual C\+\+ 6.0 이전에는 **LoadLibrary** 및 **GetProcAddress**를 사용해야지만 런타임에 DLL을 로드할 수 있었습니다. 운영 체제는 실행 파일이나 실행 파일을 사용하는 DLL이 로드되었을 때 DLL을 로드합니다.  
  
 Visual C\+\+ 6.0부터는 DLL과 정적으로 링크할 경우 프로그램이 해당 DLL의 함수를 호출할 때까지 링커가 DLL 로드를 지연하는 옵션이 제공됩니다.  
  
 응용 프로그램에서 [\/DELAYLOAD\(가져오기 로드 지연\)](../../build/reference/delayload-delay-load-import.md) 링커 옵션을 도우미 함수\(Visual C\+\+에서 제공되는 기본 구현\)와 함께 사용하여 DLL을 지연 로드할 수 있습니다.  도우미 함수는 **LoadLibrary** 및 **GetProcAddress**를 호출하여 런타임에 DLL을 로드합니다.  
  
 다음과 같은 경우 DLL 지연 로드를 고려해야 합니다.  
  
-   프로그램이 DLL의 함수를 호출하지 않는 경우  
  
-   프로그램 실행이 거의 종료될 때까지 DLL의 함수를 호출하지 않아도 되는 경우  
  
 DLL 지연 로드는 .EXE 또는 .DLL 프로젝트를 빌드하는 동안 지정될 수 있습니다.  하나 이상의 DLL 로드를 지연시키는 .DLL 프로젝트는 Dllmain에서 지연 로드 진입점을 호출하지 않아야 합니다.  
  
 다음 항목에서 DLL의 지연 로드에 대해 설명합니다.  
  
-   [지연 로드할 DLL 지정](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [지연 로드된 DLL의 명시적 언로드](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [지연 로드된 DLL에 대한 모든 가져오기 로드](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [가져오기 바인딩](../../build/reference/binding-imports.md)  
  
-   [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)  
  
-   [지연 로드된 가져오기 덤프](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [DLL 지연 로드의 제약 조건](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [도우미 함수 이해](http://msdn.microsoft.com/ko-kr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)  
  
-   [사용자 도우미 함수 개발](../../build/reference/developing-your-own-helper-function.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../../build/dlls-in-visual-cpp.md)   
 [링크](../../build/reference/linking.md)