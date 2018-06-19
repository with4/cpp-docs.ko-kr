---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 배포 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6658c972b9d9cdeececd43a89ac424964d2289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358809"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 배포
이 문서에서는 ActiveX 컨트롤 재배포와 관련 된 몇 가지 문제를 설명 합니다.  
  
-   [ANSI 또는 유니코드 제어 버전](#_core_ansi_or_unicode_control_versions)  
  
-   [ActiveX 컨트롤 및 재배포 가능 Dll 설치](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [컨트롤 등록](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI 또는 유니코드 제어 버전  
 ANSI 또는 유니코드 버전 제어, 또는 둘 다의 제공 여부를 결정 해야 합니다. 이 결정의 ANSI 및 유니코드 문자 집합 이식성 요소를 기반으로 합니다.  
  
 모든 Win32 운영 체제에서 작동 하는 ANSI 컨트롤을 다양 한 Win32 운영 체제 간의 이식성을 최대화할 수 있습니다. 유니코드 컨트롤에만 Windows NT (버전 3.51 이상)만 Windows 95 또는 Windows 98 작동합니다. 이식성이 ship ANSI 컨트롤 중요 합니다. 컨트롤은 Windows NT 에서만 실행 됩니다, 유니코드 컨트롤을 제공할 수 있습니다. 모두 제공 하 고 사용자의 운영 체제에 가장 적합 한 버전을 설치 하는 응용 프로그램을 선택할 수 있습니다.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX 컨트롤 및 재배포 가능 Dll 설치  
 ActiveX 컨트롤을 제공 하는 설치 프로그램 Windows 디렉터리의 특별 한 하위 만들고의 컨트롤을 설치 해야 합니다. 에 OCX 파일입니다.  
  
> [!NOTE]
>  Windows를 사용 하 여 **GetWindowsDirectory** 항상 설치 프로그램에서 API는 Windows 디렉터리의 이름을 가져올 수 있습니다. 하위 디렉터리 이름을 회사 또는 제품 이름에서 파생 될 수도 있습니다.  
  
 설치 프로그램은 Windows 시스템 디렉터리에 필요한 재배포 가능 DLL 파일을 설치 해야 합니다. Dll 사용자의 컴퓨터에 이미 있는 경우 설치 프로그램의 버전을 설치 하는 버전으로 비교 해야 합니다. 해당 버전 번호는 이미 설치 된 파일에 보다 높은 경우에 파일을 다시 설치 합니다.  
  
 없기 때문에 ActiveX 컨트롤은 OLE 컨테이너 응용 프로그램에만 사용할 수 있습니다, 컨트롤을 OLE Dll의 전체 집합을 배포할 필요가 없습니다. 포함 응용 프로그램 (또는 운영 체제 자체)에 표준 OLE Dll이 설치 되어 있는지를 가정할 수 있습니다.  
  
##  <a name="_core_registering_controls"></a> 컨트롤 등록  
 컨트롤을 사용 하려면 먼저 Windows 등록 데이터베이스에 적절 한 항목을 만들어야 합니다. 일부 ActiveX 컨트롤 컨테이너는 사용자가 새 컨트롤을 등록할 수에 대 한 메뉴 항목을 제공 하지만이 기능은 모든 컨테이너에 없을 수도 있습니다. 따라서 설치 될 때 해당 컨트롤을 등록 하 여 설치 프로그램을 할 수 있습니다.  
  
 원한다 면 대신 컨트롤을 직접 등록 하려면 설치 프로그램을 작성할 수 있습니다.  
  
 사용 하 여 **LoadLibrary** 컨트롤 DLL을 로드 하는 Windows API입니다. 를 사용 하 여 **GetProcAddress** "DllRegisterServer" 함수의 주소를 가져옵니다. 마지막으로 호출 된 `DllRegisterServer` 함수입니다. 다음 코드 예제에서는 한 가지 방법을 보여 줍니다. 여기서 `hLib` 컨트롤 라이브러리의 핸들을 저장 하 고 `lpDllEntryPoint` "DllRegisterServer" 함수의 주소를 저장 합니다.  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 컨트롤을 직접 등록의 장점은 필요가 없습니다 호출 하 고 별도 프로세스 (즉, REGSVR32)를 로드 합니다. 설치 시간을 줄일 점입니다. 또한 등록 내부 프로세스 이기 때문에 설치 프로그램에서 오류를 처리할 수 및 예측할 수 없는 상황에서 외부 프로세스 보다 더 수 있습니다.  
  
> [!NOTE]
>  설치 프로그램에서 ActiveX 컨트롤을 설치 하기 전에 호출 해야 **OleInitialize**합니다. 설치 프로그램이 완료 되 면 호출 **OleUnitialize**합니다. 이렇게 하면 OLE 시스템 Dll에 ActiveX 컨트롤을 등록 하기 위한 적절 한 상태입니다.  
  
 MFCx0.DLL 등록 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

