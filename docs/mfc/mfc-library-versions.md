---
title: MFC 라이브러리 버전 | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92568f61bb1ea219ab3ddc96f4c4687dec157c9a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931767"
---
# <a name="mfc-library-versions"></a>MFC 라이브러리 버전

MFC 라이브러리 버전을 사용할 수를 지 원하는 ANSI 싱글바이트 및 멀티 바이트 문자 집합 (MBCS) 코드 뿐만 아니라 유니코드 (u t F-16LE Windows 네이티브 문자 집합으로 인코딩 됨)를 지 원하는 버전. 각 MFC 버전 또는 정적 라이브러리를 공유 DLL로 제공 됩니다. MFC 컨트롤은 크기에 매우 민감합니다 및 해당 컨트롤이 필요 하지 않습니다는 응용 프로그램에 대 한 대화에 대 한를 해제 하는 작은 MFC 정적 라이브러리 버전 이기도 합니다. MFC 라이브러리 디버그에 사용할 수 있으며 릴리스 x86, x64 및 ARM 프로세서를 포함 하는 지원 되는 아키텍처에 대 한 버전. 응용 프로그램 (.exe 파일)을 모두 만들 수 있습니다 및 MFC 라이브러리의 모든 버전에 대 한 Dll입니다. 또한 관리 코드와 상호 작용에 대 한 컴파일된 MFC 라이브러리의 집합입니다. MFC 공유 Dll 라이브러리 이진 호환성을 나타내는 버전 번호를 포함 합니다.

## <a name="automatic-linking-of-mfc-library-versions"></a>MFC 라이브러리 버전 자동 링크

자동으로 MFC 헤더 파일 빌드 환경에 정의 된 값에 따라 올바른 버전의 MFC 라이브러리에 링크를 확인 합니다. MFC 헤더 파일 특정 버전의 MFC 라이브러리에 연결 하 여 링커가 컴파일러 지시문을 추가 합니다.

예를 들어 AFX 합니다. H 헤더 파일의 전체 정적, 제한, 정적 또는 공유 MFC의 DLL 버전;에 연결할 링커에 지시 ANSI/MBCS 또는 유니코드 버전입니다. 및 빌드 구성에 따라 디버그 또는 소매 버전:

```cpp
#ifndef _AFXDLL
    #ifdef _AFX_NO_MFC_CONTROLS_IN_DIALOGS
        #ifdef _DEBUG
            #pragma comment(lib, "afxnmcdd.lib")
        #else
            #pragma comment(lib, "afxnmcd.lib")
        #endif
        #pragma comment(linker, "/include:__afxNoMFCControlSupportInDialogs")
        #pragma comment(linker, "/include:__afxNoMFCControlContainerInDialogs")
    #endif
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "nafxcwd.lib")
        #else
            #pragma comment(lib, "nafxcw.lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "uafxcwd.lib")
        #else
            #pragma comment(lib, "uafxcw.lib")
        #endif
    #endif
#else
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "d.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "d.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER ".lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER ".lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "ud.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "ud.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "u.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "u.lib")
        #endif
    #endif
#endif
```

또한 MFC 헤더 파일 MFC 라이브러리, Win32 라이브러리, OLE 라이브러리, 샘플 로부터 빌드된 OLE 라이브러리, ODBC 라이브러리 및 등을 비롯 한 모든 필수 라이브러리에 링크 하도록 지시문이 포함 됩니다. 

## <a name="ansi-mbcs-and-unicode"></a>ANSI, MBCS 및 유니코드

ANSI/MBCS MFC 라이브러리 버전 모두 단일 바이트 문자 집합 ASCII, u를 지원 하 고 Shift JIS 등 멀티 바이트 문자 집합입니다. 유니코드 MFC 라이브러리 버전 u t F-16LE 와이드 문자 인코딩된 형식으로 유니코드를 지원 합니다. U t F-8 인코딩된 유니코드 지원에 대 한 ANSI/MBCS 라이브러리 버전의 MFC 사용 합니다.

IDE에서 유니코드 문자열 및 문자 지원 단일 바이트, 멀티 바이트 또는 와이드 문자를 사용 하 여 프로젝트 구성을 설정 하려면는 **프로젝트 속성** 대화 상자. 에 **구성 속성** > **일반** 페이지에서 설정 된 **문자 집합** 속성을 **설정 하지** 사용 하는 단일 바이트 문자 집합입니다. 속성을 설정 **멀티 바이트 문자 집합 사용** 멀티 바이트 문자 집합을 사용 하도록 또는 **유니코드 문자 집합 사용** u t F-16으로 인코딩된 유니코드를 사용 하도록 합니다.

전처리기 기호를 사용 하는 MFC 프로젝트 \_유니코드를 나타내는 u t F-16 와이드 문자 유니코드 지원 및 \_MBCS를 나타내기 위해 MBCS 지원 합니다. 이러한 옵션은 프로젝트에서 함께 사용할 수 없습니다.

## <a name="mfc-static-library-naming-conventions"></a>MFC 정적 라이브러리 명명 규칙

MFC에 대 한 정적 라이브러리는 다음과 같은 명명 규칙을 사용합니다. 라이브러리 이름은

> *u*AFX*c**d*.LIB

여기서 기울임꼴 소문자로 표시 문자는 그 의미는 다음 표와 지정자에 대 한 자리 표시자.

|지정자|값 및 의미|
|---------------|-------------------------|
|*u*|ANSI/MBCS (N) 또는 유니코드 (U). 대화 상자에서 MFC 컨트롤 사용 하지 않는 버전에 대 한 생략|
|*c*|MFC 컨트롤 (NMCD) 없이 또는 대화 상자 (CW) 버전|
|*d*|디버그 또는 릴리스: D = Debug; 릴리스에 대 한 지정자를 생략 합니다.|

다음 표에 나열 된 모든 라이브러리가 포함 됩니다. 지원 되는 빌드가 아키텍처에 대 한 \atlmfc\lib 디렉터리에 미리 작성 된 합니다.

|라이브러리|설명|
|-------------|-----------------|
|NAFXCW.LIB|MFC 동적 연결 라이브러리, 릴리스 버전|
|NAFXCWD.LIB|MFC 동적 연결 라이브러리, 디버그 버전|
|UAFXCW.LIB|유니코드를 지 원하는, 릴리스 버전 MFC 정적 연결 라이브러리|
|UAFXCWD.LIB|유니코드 지원 디버그 버전 MFC 정적 연결 라이브러리|
|AFXNMCD.LIB|MFC 대화 상자 컨트롤, 릴리스 버전 없이 MFC 정적 연결 라이브러리|
|AFXNMCDD.LIB|MFC 대화 상자 컨트롤, 디버그 버전 없이 MFC 정적 연결 라이브러리|

디버거 파일 같은 기본 이름과 및.pdb 확장명을 정적 라이브러리를 각각에 대해 사용할 수 있습니다.

## <a name="mfc-shared-dll-naming-conventions"></a>MFC 공유 DLL 명명 규칙

MFC 공유 Dll도 구조적된 명명 규칙을 따릅니다. 이렇게 하면 보다 쉽게는 DLL 또는 라이브러리를 사용 해야 각 용도 대 한 알 수 있습니다.

MFC dll *버전* 이진 호환성을 나타내는 번호입니다. 다른 라이브러리 및 프로젝트 내에서 호환성을 보장 하기 위해 컴파일러 도구 집합으로 같은 버전이 MFC Dll을 사용 합니다.

|DLL|설명|
|---------|-----------------|
|MFC*버전*합니다. DLL|MFC DLL, ANSI 또는 MBCS 릴리스 버전|
|MFC*버전*U.DLL|MFC DLL, 유니코드 릴리스 버전|
|MFC*version*D.DLL|MFC DLL, ANSI 또는 MBCS 디버그 버전|
|MFC*버전*UD 합니다. DLL|MFC DLL, 유니코드 디버그 버전|
|MFCM*version*.DLL|MFC DLL Windows Forms 컨트롤을 ANSI 또는 MBCS 릴리스 버전|
|MFCM*version*U.DLL|MFC DLL을 Windows Forms 컨트롤, 유니코드 릴리스 버전|
|MFCM*version*D.DLL|MFC DLL Windows Forms 컨트롤을 ANSI 또는 MBCS 디버그 버전|
|MFCM*버전*UD 합니다. DLL|MFC DLL을 Windows Forms 컨트롤, 유니코드 디버그 버전|

응용 프로그램 또는 MFC 확장 Dll 이러한 공유 Dll을 사용 하는 빌드하는 데 필요한 가져오기 라이브러리 DLL과 같은 기본 이름을 갖지만.lib 파일 이름 확장명이 있습니다. 공유 Dll을 사용 하면 작은 정적 라이브러리 여전히와 연결 되어야 합니다 코드 이 라이브러리 MFCS 라는*버전*{U} {D}.lib입니다.

동적으로 연결할 공유 DLL 버전의 MFC 응용 프로그램에서 또는 MFC 확장 DLL에서에서 여부, 경우에 일치 하는 MFC 포함 해야*버전*합니다. DLL 또는 MFC*버전*U.DLL 제품을 배포 합니다.

목록이 응용 프로그램과 함께 배포할 수 있는 Visual c + + Dll에 대 한 참조 [Microsoft Visual Studio 2017 및 Microsoft Visual Studio 2017 SDK (포함 유틸리티 및 BuildServer 파일)에 대 한 배포 가능한 코드](http://go.microsoft.com/fwlink/p/?LinkId=823098)합니다.

MFC의 MBCS 및 유니코드 지원에 대 한 자세한 내용은 참조 하십시오. [유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.

## <a name="dynamic-link-library-support"></a>동적 연결 라이브러리 지원

MFC 및 비 MFC 실행 파일에서 사용할 수 있는 Dll을 만드는 중 하나는 정적 또는 공유 동적 MFC 라이브러리를 사용할 수 있습니다. 이 "기본 Dll" 또는 "기본 MFC Dll" 라고, MFC 확장 Dll만 될 수 있는 구분 하기 위해에서 사용 하는 MFC 응용 프로그램 및 MFC Dll입니다. MFC 정적 라이브러리를 사용 하 여 작성 된 DLL 라고는 USRDLL 이전 참조에 전처리기 기호를 정의 하는 MFC DLL 프로젝트  **\_USRDLL**합니다. 사용 하 여 MFC 공유 Dll DLL 라고는 AFXDLL 이전 참조에 전처리기 기호를 정의 하기 때문에  **\_AFXDLL**합니다.

MFC 정적 라이브러리에 연결 하 여 DLL 프로젝트를 만들 때 DLL은 MFC 공유 Dll 하지 않고 배포할 수 있습니다. DLL 프로젝트 MFC 가져오기 라이브러리에 연결 하는 경우*버전*합니다. LIB 또는 MFC*버전*U.LIB를 배포 해야 일치 하는 MFC 공유 DLL MFC*버전*합니다. DLL 또는 MFC*버전*U.DLL DLL 함께 합니다. 자세한 내용은 참조 [Dll](../build/dlls-in-visual-cpp.md)합니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)  
