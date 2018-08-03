---
title: Win 32 프로젝트 마법사, 응용 프로그램 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.appwiz.win32.appset
dev_langs:
- C++
helpviewer_keywords:
- application settings [C++]
- Win32 Project Wizard, application settings
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6d2cd31306baaa0d9c8f137122fed1d4ae97295
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464693"
---
# <a name="application-settings-win-32-project-wizard"></a>Win32 프로젝트 마법사, 응용 프로그램 설정
마법사의이 페이지를 사용 하여 Win32 프로젝트에 대한 옵션을 설정 합니다.  
  
 **응용 프로그램 종류**  
 지정 된 응용 프로그램 유형을 만듭니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**콘솔 응용 프로그램**|콘솔 응용 프로그램을 만듭니다. 콘솔 프로그램은 콘솔 창에서 문자 모드 지원을 제공하는 [콘솔 함수](https://msdn.microsoft.com/library/ms813137.aspx), 로 개발됩니다. Visual c + + [런타임 라이브러리](../c-runtime-library/c-run-time-library-reference.md) 도 출력을 제공 하 고 같은 표준 I/O 기능을 사용 하 여 콘솔 창에서 입력 `printf_s()` 고 `scanf_s()`입니다. 콘솔 응용 프로그램에 그래픽 사용자 인터페이스가 없습니다. .exe로 컴파일되고 명령줄에서 독립 실행형 응용 프로그램으로 실행할 수 있습니다.<br /><br /> Windows 응용 프로그램에 MFC 또는 ATL 지원을 추가할 수 없습니다.|  
|**Windows 응용 프로그램**|Win32 프로그램을 만듭니다. Win32 프로그램은 실행 가능한 응용 프로그램 (EXE)으로 C 또는 C++로 작성되고, Win32 API를 호출하여 그래픽 사용자 인터페이스를 만들 수 있습니다.<br /><br /> MFC를 추가할 수 없습니다. 또는 Windows 응용 프로그램에 ATL을 지원합니다.|  
|**DLL**|Win32 동적 연결 라이브러리 (DLL)를 만듭니다. Win32 DLL은 C 또는 C++로 작성된 바이너리 파일로, MFC 클래스 대신 Win32 API를 호출하며 동시에 여러 응용 프로그램에서 사용할 수 있는 함수의 공유 라이브러리 역할을 합니다.<br /><br /> DLL 응용 프로그램에 MFC 또는 ATL 지원을 추가할 수 없습니다. DLL에서 기호를 내보내도록 할 수 있습니다.|  
|**정적 라이브러리**|정적 라이브러리를 만듭니다. 정적 라이브러리는 개체와 개체 함수 그리고 실행 파일을 빌드할 때 프로그램에 연결되는 데이터를 포함하는 파일입니다. 이 항목에서는 시작 파일을 만드는 방법과 정적 라이브러리에 대한 [프로젝트 속성](../ide/property-pages-visual-cpp.md)에 대해 설명합니다.  정적 라이브러리 파일은 다음과 같은 이점을 제공합니다.<br /><br /> -Win32 정적 라이브러리는 작업 중인 응용 프로그램에서 MFC 클래스 대신 Win32 API를 호출하는 경우에 유용합니다.<br />-Windows 응용 프로그램의 나머지 부분의 C 또는 C++로 작성 여부와 관계없이 연결된 프로세스는 동일합니다.<br />-비 MFC 프로그램과 MFC 기반 프로그램 모두 정적 라이브러리를 연결할 수 있습니다.|  
  
 **추가 옵션**  
 지원 및 해당 형식에 따라 응용 프로그램에 대 한 옵션을 정의합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**빈 프로젝트**|프로젝트 파일이 비어 있는지를 확인합니다.  소스 코드 파일 (예:.cpp 파일, 헤더 파일, 아이콘, 도구 모음, 대화 상자 등)의 집합이 있고 Visual C++ 개발 환경에서 프로젝트를 만들려고 할 경우 먼저 빈 프로젝트를 만든 다음 파일을 프로젝트에 추가해야 합니다.<br /><br /> 이 옵션은 정적 라이브러리 프로젝트를 선택할 수 없는 경우 사용합니다.|  
|**내보내기 기호**|DLL 프로젝트에서 기호를 내보내도록 지정 합니다.|  
|**미리 컴파일된 헤더**|정적 라이브러리 프로젝트는 미리 컴파일된 헤더를 지정 합니다.|  
|보안 개발 수명 주기 (SDL) 검사|SDL에 대 한 자세한 내용은 참조 하세요. [Microsoft Security Development Lifecycle (SDL) 프로세스 지침](../build/reference/sdl-enable-additional-security-checks.md)|  
  
 **추가 지원**  
 Visual C++에서 제공되는 라이브러리에 대한 지원을 추가합니다.   
  
|옵션|설명|  
|------------|-----------------|  
|**ATL**|액티브 템플릿 라이브러리 (ATL)의 클래스를 추가 지원하여 프로젝트를 빌드합니다.  Win32 콘솔 응용 프로그램에만 해당됩니다.<br /><br /> **참고** 이 옵션은 ATL 코드 마법사를 이용하여 ATL 개체를 추가할 수 있도록 지원하지 않습니다.  ATL 프로젝트나 MFC 프로젝트에서만 ATL 개체를 추가할 수 있습니다.|  
|**MFC**|MFC 라이브러리에 대한 지원을 프로젝트에 빌드합니다.  Win32 콘솔 응용 프로그램 및 정적 라이브러리만 해당됩니다.||  
  
## <a name="see-also"></a>참고 항목  
 [Win32 응용 프로그램 마법사](../windows/win32-application-wizard.md)   