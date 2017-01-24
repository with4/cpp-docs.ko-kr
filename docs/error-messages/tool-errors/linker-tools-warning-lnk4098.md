---
title: "링커 도구 경고 LNK4098 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4098"
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'library' defaultlib가 다른 라이브러리와 충돌합니다. \/NODEFAULTLIB:library를 사용하십시오.  
  
 호환되지 않는 라이브러리에 링크하려고 했습니다.  
  
> [!NOTE]
>  런타임 라이브러리에는 여러 형식이 혼합 사용되지 않도록 하는 지시문이 들어 있는데  여러 형식이나 디버그\/비디버그 버전의 런타임 라이브러리를 동일한 프로그램에서 사용하려고 하면 이 경고가 발생합니다.  예를 들어, 어떤 종류의 런타임 라이브러리를 사용하는 파일을 컴파일하고 다른 종류의 런타임 라이브러리를 사용하는 파일을 컴파일한 다음\(예: 단일 스레드 라이브러리와 다중 스레드 라이브러리\) 이 둘을 링크시키려고 하면 이 경고가 발생합니다.  동일한 런타임 라이브러리를 사용하는 소스 파일을 컴파일해야 합니다.  자세한 내용은 [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md)\(**\/MD**, **\/MT**, **\/LD**\) 컴파일러 옵션을 참조하십시오.  
  
 링커의 [\/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md) 스위치를 사용하여 링커가 검색 중인 라이브러리를 확인할 수 있습니다.  예를 들어, LNK4098이 발생하여 단일 스레드된 비디버그 런타임 라이브러리를 사용하는 실행 파일을 만들려는 경우에는 **\/VERBOSE:LIB** 옵션을 사용하여 링커에서 검색 중인 라이브러리를 확인하십시오.  링커는 검색한 라이브러리로 LIBC.lib를 출력하며 LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib 또는 MSVCRTD.lib는 출력하지 않습니다.  무시할 각 라이브러리에 대해 [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)를 사용하여 링커가 잘못된 런타임 라이브러리를 무시하도록 할 수 있습니다.  
  
 다음 표는 사용할 런타임 라이브러리에 따라 무시해야 하는 라이브러리를 보여 줍니다.  
  
|사용할 런타임 라이브러리|무시해야 하는 라이브러리|  
|-------------------|-------------------|  
|단일 스레드\(libc.lib\)|libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|다중 스레드\(libcmt.lib\)|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|DLL을 사용하는 다중 스레드\(msvcrt.lib\)|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|디버그 단일 스레드\(libcd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|디버그 다중 스레드\(libcmtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|DLL을 사용하는 디버그 다중 스레드\(msvcrtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 예를 들어, 이 경고가 발생한 경우와 비디버그, 단일 스레드 버전의 런타임 라이브러리를 사용하는 실행 파일을 만들려는 경우에는 링커에 다음 옵션을 사용하면 됩니다.  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```