---
title: "Windows 스토어 앱, Windows 런타임 및 C 런타임 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c75d66fcbe9ef437980878e7789a82dc94b68573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Windows 스토어 앱, Windows 런타임 및 C 런타임
[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱은 [!INCLUDE[win8](../build/reference/includes/win8_md.md)]에서 실행되는 Windows 런타임에서 실행하는 프로그램입니다.  Windows 런타임은 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱에서 사용할 수 있는 함수, 변수 및 리소스를 제어하는 신뢰할 수 있는 환경입니다. 그러나 기본적으로 Windows 런타임 제한 때문에 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱의 대부분의 CRT(C 런타임 라이브러리) 기능을 사용할 수 없습니다.  
  
 Windows 런타임에서는 다음 CRT 기능을 지원하지 않습니다.  
  
-   지원되지 않는 기능과 관련된 대부분의 CRT 함수  
  
     예를 들어 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램은 루틴의 `exec` 및 `spawn` 패밀리를 사용하여 프로세스를 만들 수 없습니다.  
  
     [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 CRT 함수가 지원되지 않는 경우 이러한 사실이 해당 참조 문서에 기록됩니다.  
  
-   대부분의 멀티바이트 문자 및 문자열 함수  
  
     그러나 유니코드 텍스트와 ANSI 텍스트 모두 지원됩니다.  
  
-   콘솔 응용 프로그램 및 명령줄 인수  
  
     그러나 일반적인 데스크톱 응용 프로그램에서도 콘솔 및 명령줄 인수를 지원합니다.  
  
-   환경 변수.  
  
-   현재 작업 디렉터리의 개념  
  
-   정적으로 CRT에 연결되고 [/MT](../build/reference/md-mt-ld-use-run-time-library.md) 또는 `/MTd` 컴파일러 옵션을 사용하여 빌드된 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱 및 DLL  
  
     즉, CRT의 다중 스레드 정적 버전을 사용하는 응용 프로그램입니다.  
  
-   [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 사용하여 빌드한 앱  
  
     즉, CRT의 디버그, 다중 스레드 및 DLL 전용 버전입니다. 이러한 응용 프로그램은 [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)]에서 지원되지 않습니다.  
  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱에서 사용할 수 없는 CRT 함수의 전체 목록 및 대체 기능에 대한 제안을 보려면 [/ZW에는 CRT 함수가 지원 안 됨](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [호환성](../c-runtime-library/compatibility.md)   
 [Windows 런타임 지원되지 않는 CRT 함수](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)