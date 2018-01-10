---
title: "링커 도구 경고 LNK4098 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4098
dev_langs: C++
helpviewer_keywords: LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b199c19417d7d3be866109fff7361fb4ead959d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4098"></a>링커 도구 경고 LNK4098
다른 라이브러리;의 사용과 defaultlib 'library' 충돌 합니다를 사용 하 여  
  
 호환 되지 않는 라이브러리와 링크 하려고 합니다.  
  
> [!NOTE]
>  런타임 라이브러리 여러 형식이 혼합을 방지 하기 위해 지시문이 들어 있습니다. 이 다른 형식을 사용 하거나 디버그 하려고 하는 경우 경고 및 디버그가 아닌 버전 런타임 라이브러리의 동일한 프로그램에서 표시 됩니다. 예를 들어, 사용 하 고 다른 종류의 런타임 라이브러리 (예: 다중 스레드 및 단일 스레드) 다른 종류를 사용 하 고 연결 하려고 했습니다. 파일을 컴파일한 경우이 경고가 발생 합니다. 모든 소스 파일을 동일한 런타임 라이브러리를 사용 하 여 컴파일해야 합니다. 참조는 [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/LD**) 컴파일러 옵션을 참조 하십시오.  
  
 링커의 사용할 수 있습니다 [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) 스위치 링커가 검색 하는 라이브러리를 확인할 수 있습니다. 비디버그 런타임 라이브러리를 사용 하 여 LNK4098 및을 사용 하는 예를 들어는 단일 스레드 실행 파일을 만들어 나타나면는 **/verbose: lib** 라이브러리는 링커가 검색 하는 옵션입니다. 링커는 검색 된 라이브러리로 LIBC.lib 및 없는 LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib, 또는 MSVCRTD.lib 인쇄 해야 합니다. 사용 하 여 잘못 된 런타임 라이브러리를 무시 하도록 링커에 지시할 수 있습니다 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 무시 하려는 각 라이브러리에 대 한 합니다.  
  
 아래 표에 런타임 라이브러리에 따라 사용 하려는 라이브러리를 무시 해야 합니다.  
  
|이 런타임 라이브러리를 사용 하려면|이러한 라이브러리를 무시 합니다.|  
|-----------------------------------|----------------------------|  
|단일 스레드 (libc.lib)|libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|다중 스레드 (libcmt.lib)|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|다중 스레드 DLL (msvcrt.lib)를 사용 하 여|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|단일 스레드 디버그 (libcd.lib)|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|디버그 다중 스레드 (libcmtd.lib)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|다중 스레드 DLL (msvcrtd.lib)를 사용 하 여 디버그|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 예를 들어이 경고가 발생 하는 경우 디버그가 아닌, 단일 스레드 런타임 라이브러리의 버전을 사용 하는 실행 파일을 만들려고 한다고 링커 다음 옵션을 사용할 수 있습니다.  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```