---
title: "/DEBUGTYPE(디버그 정보 옵션) | Microsoft Docs"
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
  - "/debugtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEBUGTYPE 링커 옵션"
  - "DEBUGTYPE 링커 옵션"
  - "-DEBUGTYPE 링커 옵션"
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEBUGTYPE(디버그 정보 옵션)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/DEBUGTYPE 옵션은 \/DEBUG 옵션으로 생성된 디버깅 정보의 형식을 지정합니다.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## 인수  
 CV  
 기호, 줄 번호 및 PDB 파일의 기타 개체 컴파일 정보에 대한 디버그 정보를 내보내도록 링커에 지시합니다.  기본적으로 이 옵션은 **\/DEBUG**를 지정하고 **\/DEBUGTYPE**을 지정하지 않은 경우에 사용됩니다.  
  
 PDATA  
 PDB 파일의 디버그 스트림 정보에 .pdata 및 .xdata 항목을 추가하도록 링커에 지시합니다.  기본적으로 이 옵션은 **\/DEBUG**와 **\/DRIVER** 옵션을 모두 지정한 경우에 사용됩니다.  자체적으로 **\/DEBUGTYPE:PDATA**를 지정하는 경우 링커는 PDB 파일에 디버깅 기호를 자동으로 포함합니다.  **\/DEBUGTYPE:PDATA,FIXUP**을 지정하는 경우 링커는 PDB 파일에 디버깅 기호를 포함하지 않습니다.  
  
 FIXUP  
 PDB 파일의 디버그 스트림 정보에 재배치 테이블 항목을 추가하도록 링커에 지시합니다.  기본적으로 이 옵션은 **\/DEBUG**와 **\/PROFILE** 옵션을 모두 지정한 경우에 사용됩니다.  **\/DEBUGTYPE:FIXUP** 또는 **\/DEBUGTYPE:FIXUP,PDATA**를 지정하는 경우 링커는 PDB 파일에 디버깅 기호를 포함하지 않습니다.  
  
 **\/DEBUGTYPE**에 대한 인수는 쉼표로 구분하여 순서대로 결합할 수 있습니다.  **\/DEBUGTYPE** 옵션 및 해당 인수는 대\/소문자를 구분하지 않습니다.  
  
## 설명  
 **\/DEBUGTYPE** 옵션을 사용하여 재배치 테이블 데이터 또는 .pdata 및 .xdata 헤더 정보를 디버깅 스트림에 포함하도록 지정합니다.  그러면 링커는 커널 모드 코드를 중단할 때 커널 디버거에 표시되는 사용자 모드 코드에 대한 정보를 포함할 수 있습니다.  **FIXUP**을 지정하는 경우 디버깅 기호를 사용할 수 있도록 설정하려면 **CV** 인수를 포함합니다.  
  
 사용자 모드에서 응용 프로그램에 일반적인 코드를 디버그하려면 **\/DEBUGTYPE** 옵션이 필요하지 않습니다.  기본적으로 디버깅 출력\([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\)을 지정하는 컴파일러 스위치는 Visual Studio 디버거에 필요한 모든 정보를 내보냅니다.  **\/DEBUGTYPE:PDATA** 또는 **\/DEBUGTYPE:CV,PDATA,FIXUP**을 사용하여 장치 드라이버용 구성 앱과 같이 사용자 모드 및 커널 모드 구성 요소를 결합하는 코드를 디버그합니다.  커널 모드 디버거에 대한 자세한 내용은 [Windows용 디버깅 도구\(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)\(영문\)를 참조하세요.  
  
## 참고 항목  
 [\/DEBUG\(디버깅 정보 생성\)](../../build/reference/debug-generate-debug-info.md)   
 [\/DRIVER\(Windows NT 커널 모드 드라이버\)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [\/PROFILE\(성능 도구 프로파일러\)](../../build/reference/profile-performance-tools-profiler.md)   
 [Windows용 디버깅 도구\(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)