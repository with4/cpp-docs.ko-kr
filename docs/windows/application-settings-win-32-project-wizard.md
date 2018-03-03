---
title: "Win32 프로젝트 마법사, 응용 프로그램 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.win32.appset
dev_langs:
- C++
helpviewer_keywords:
- application settings [C++]
- Win32 Project Wizard, application settings
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f93e81d5d030112f436ad93a53c2a65854b38f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="application-settings-win-32-project-wizard"></a>Win32 프로젝트 마법사, 응용 프로그램 설정
마법사의이 페이지를 사용 하 여 Win32 프로젝트에 대 한 옵션을 설정 합니다.  
  
 **응용 프로그램 종류**  
 지정 된 응용 프로그램 유형을 만듭니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**콘솔 응용 프로그램**|콘솔 응용 프로그램을 만듭니다. 콘솔 프로그램을 사용 하 여 개발한 [콘솔 함수](https://msdn.microsoft.com/en-us/library/ms813137.aspx), 콘솔 창에서 지 원하는 문자 모드를 제공 합니다. Visual c + + [런타임 라이브러리](../c-runtime-library/c-run-time-library-reference.md) 또한 출력을 제공 하 고와 같은 표준 I/O 함수를 사용 하 여 콘솔 창에서 입력 **printf_s()** 및 **scanf_s()**합니다. 콘솔 응용 프로그램에 그래픽 사용자 인터페이스가 없습니다. .Exe로 컴파일되고 명령줄에서 독립 실행형 응용 프로그램으로 실행할 수 있습니다.<br /><br /> 콘솔 응용 프로그램을 MFC 및 ATL 지원을 추가할 수 있습니다.|  
|**Windows 응용 프로그램**|Win32 프로그램을 만듭니다. Win32 프로그램은 실행 가능한 응용 프로그램 (EXE)로 작성 된 C 또는 c + + Win32 API에 대 한 호출을 사용 하 여 그래픽 사용자 인터페이스를 만들 수 있습니다.<br /><br /> MFC를 추가할 수 없습니다 또는 Windows 응용 프로그램에 ATL 지원 합니다.|  
|**DLL**|Win32 동적 연결 라이브러리 (DLL)를 만듭니다. Win32 DLL은 C 또는 c + +, MFC 클래스 대신 Win32 api 호출을 사용 하 고 동시에 여러 응용 프로그램에서 사용할 수 있는 함수의 공유 라이브러리로 사용 하는 작성 된 이진 파일입니다.<br /><br /> MFC를 추가할 수 없습니다 또는 DLL 응용 프로그램에 ATL 지원 합니다. DLL에서 기호를 내보내도록 나타낼 수 있습니다.|  
|**정적 라이브러리**|정적 라이브러리를 만듭니다. 정적 라이브러리는 개체 함수 및 실행 파일을 빌드할 때 프로그램에 연결 되는 데이터를 포함 하는 파일입니다. 이 항목에서는 시작 파일을 만드는 방법에 설명 하 고 [프로젝트 속성](../ide/property-pages-visual-cpp.md) 정적 라이브러리에 대 한 합니다. 정적 라이브러리 파일에는 다음과 같은 이점을 제공합니다.<br /><br /> -Win32 정적 라이브러리는 응용 프로그램에서 작업 하는 MFC 클래스 대신 Win32 API를 호출 하는 경우에 유용 합니다.<br />-연결 프로세스는 Windows 응용 프로그램의 나머지 부분에는 C 또는 c + +로 작성 된 동일 합니다.<br />-비 MFC 프로그램 또는 MFC 기반 프로그램에 정적 라이브러리를 연결할 수 있습니다.|  
  
 **추가 옵션**  
 지원 및 해당 형식에 따라 응용 프로그램에 대 한 옵션을 정의합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**빈 프로젝트**|프로젝트 파일은 비어 있는지를 지정 합니다. 소스 코드 파일 (예:.cpp 파일, 헤더 파일, 아이콘, 도구 모음, 대화 상자 및 등)의 집합을 있고 Visual c + + 개발 환경에서 프로젝트를 만들려고 할 경우 먼저 빈 프로젝트를 만든 다음 파일을 프로젝트에 추가 해야 있습니다.<br /><br /> 이 옵션을이 선택 정적 라이브러리 프로젝트에 사용할 수 없는 경우 합니다.|  
|**내보내기 기호**|DLL 프로젝트에서 기호를 내보내도록 지정 합니다.|  
|**미리 컴파일된 헤더**|정적 라이브러리 프로젝트에서 미리 컴파일된 헤더 사용 하도록 지정 합니다.|  
|보안 SDL (Development Lifecycle) 검사|SDL에 대 한 자세한 내용은 참조 [Microsoft 보안 SDL (Development Lifecycle) 프로세스 지침](../build/reference/sdl-enable-additional-security-checks.md)|  
  
 **에 대 한 지원 추가**  
 Visual c + +에서 제공 되는 라이브러리 중 하나에 대 한 지원을 추가 합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**ATL**|클래스에는 ATL 액티브 템플릿 라이브러리 ()에 대 한 지원을 프로젝트에 빌드합니다. Win32 콘솔 응용 프로그램에만 합니다.<br /><br /> **참고** 이 옵션 ATL를 사용 하 여 ATL 개체 마법사 코드를 추가 하기 위한 지원을 나타내지 않습니다. ATL 프로젝트에만 ATL 개체를 추가할 수 있습니다 또는 ATL과 MFC 프로젝트를 지원 합니다.|  
|**MFC**|Microsoft Foundation 클래스 (MFC) 라이브러리에 대 한 지원을 프로젝트에 빌드합니다. Win32 콘솔 응용 프로그램 및 정적 라이브러리만 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Win32 응용 프로그램 마법사](../windows/win32-application-wizard.md)   
