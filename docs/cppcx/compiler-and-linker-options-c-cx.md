---
title: "컴파일러 및 링커 옵션(C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 및 링커 옵션(C++-CX)
환경 변수, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 컴파일러 옵션 및 링커 옵션은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]용 앱의 빌드를 지원합니다.  
  
## 라이브러리 경로  
 %LIBPATH% 환경 변수는 .winmd 파일을 검색할 기본 경로를 지정합니다.  
  
## 컴파일러 옵션  
  
|옵션|설명|  
|--------|--------|  
|[\/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> \/ZW:nostdlib|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 언어 확장을 사용합니다.<br /><br /> `nostdlib` 매개 변수를 사용하면 컴파일러에서 미리 정의된 표준 검색 경로를 사용하여 어셈블리 및 .winmd 파일을 찾지 못합니다.<br /><br /> [\/ZW](../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션은 다음 컴파일러 옵션을 암시적으로 지정합니다.<br /><br /> -   [\/FI](../build/reference/fi-name-forced-include-file.md) vccorlib.h \- 컴파일러에 필요한 다양한 형식을 정의하는 vccorlib.h 헤더 파일을 강제로 포함합니다.<br />-   [\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) Windows.winmd \- [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서 다양한 형식을 정의하고 운영 체제에서 제공되는 Windows.winmd 메타데이터 파일을 강제로 포함합니다.<br />-   [\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) Platform.winmd \- 네임스페이스의 Platform 패밀리에서 대부분 형식을 정의하고 컴파일러에서 제공되는 Platform.winmd 메타데이터 파일을 강제로 포함합니다.|  
|[\/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|*dir* 매개 변수로 지정되는 디렉터리를 컴파일러에서 어셈블리 및 .winmd 파일을 찾는 데 사용하는 검색 경로에 추가합니다.|  
|[\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) *파일*|지정된 모듈 또는 .winmd 파일을 강제로 포함합니다. 즉, 소스 코드에서 `#using`*file*을 지정할 필요가 없습니다. 컴파일러에서는 고유한 Windows 메타데이터 파일, Platform.winmd를 자동으로 강제 포함합니다.|  
|\/D "WINAPI\_FAMILY\=2"|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]과 호환되는 Win32 SDK의 하위 집합을 사용할 수 있게 하는 정의를 만듭니다.|  
  
## 링커 옵션  
  
|옵션|설명|  
|--------|--------|  
|\/APPCONTAINER\[:NO\]|실행 파일을 appcontainer에서\(만\) 실행 가능으로 표시합니다.|  
|\/WINMD\[:{NO&#124;ONLY}\]|.winmd 파일 및 연결된 이진 파일을 내보냅니다. .winmd를 내보내려면 이 옵션을 링커에 전달해야 합니다.<br /><br /> **NO**—.winmd 파일을 내보내지 않지만 이진 파일을 내보냅니다.<br /><br /> **ONLY**—.winmd 파일을 내보내지만 이진 파일을 내보내지 않습니다.|  
|\/WINMDFILE:*filename*|기본 .winmd 파일 이름 대신 내보낼 .winmd 파일의 이름입니다. 명령줄에서 여러 파일 이름을 지정하면 마지막 이름이 사용됩니다.|  
|\/WINMDDELAYSIGN\[:NO\]|.winmd 파일에 부분적으로 서명하고 공개 키를 이진 파일에 삽입합니다.<br /><br /> **NO**—\(기본값\) .winmd 파일에 서명하지 않습니다.<br /><br /> \/WINMDKEYFILE 또는 \/WINMDKEYCONTAINER도 지정하지 않으면 \/WINMDDELAYSIGN은 아무런 효과가 없습니다.|  
|\/WINMDKEYCONTAINER:*name*|어셈블리에 서명할 키 컨테이너를 지정합니다.*name* 매개 변수는 메타데이터 파일에 서명하는 데 사용되는 키 컨테이너에 해당합니다.|  
|\/WINMDKEYFILE:*filename*|어셈블리에 서명할 키 또는 키 쌍을 지정합니다.*filename* 매개 변수는 메타데이터 파일에 서명하는 데 사용되는 키에 해당합니다.|  
  
## 주의  
 **\/ZW**를 사용하면 컴파일러는 CRT\(C 런타임\)의 DLL 버전에 자동으로 연결됩니다. 정적 라이브러리 버전에 연결할 수 없고 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱에서 허용되지 않는 CRT 함수를 사용하면 컴파일 시간 오류가 발생합니다.  
  
## 참고 항목  
 [응용 프로그램 및 라이브러리 빌드](../cppcx/building-apps-and-libraries-c-cx.md)