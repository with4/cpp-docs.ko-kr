---
title: Dll 및 Visual c + + 런타임 라이브러리 동작 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: feee3d888fbf43bfd8675ccc83a04fd4e1f0b528
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392064"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll 및 Visual c + + 런타임 라이브러리 동작  
  
기본적으로 Visual c + +를 사용 하 여 동적 연결 라이브러리 (DLL)를 빌드할 때 링커 Visual c + + 런타임 라이브러리 (VCRuntime)에 포함 됩니다. VCRuntime 초기화 및 C/c + + 실행 파일을 종료 하는 데 필요한 코드를 포함 합니다. VCRuntime 코드 제공 호출 하는 내부 DLL 진입점 함수를 DLL로 연결 `_DllMainCRTStartup` 를 연결 하거나 프로세스나 스레드를 분리 하려면 해당 DLL에 Windows OS 메시지를 처리 하는 합니다. `_DllMainCRTStartup` 함수는 스택 버퍼 보안 설정, C 런타임 라이브러리 (CRT) 초기화 및 종료, 예: 필수 작업을 수행 하 고 정적 및 전역 개체에 대 한 생성자 및 소멸자를 호출 합니다. `_DllMainCRTStartup` 또한 호출 후크 WinRT, MFC 및 ATL 자신의 초기화 및 종료를 수행 하는 등의 다른 라이브러리에 대 한 함수입니다. 이 초기화, CRT 및 다른 라이브러리도 정적 변수를 없이 초기화 되지 않은 상태로 남아 있을 것. DLL이 동적으로 연결 된 CRT DLL 또는 정적으로 연결 된 CRT를 사용 하는지 여부를 동일한 VCRuntime 내부 초기화 및 종료 루틴 호출 됩니다.  
  
## <a name="default-dll-entry-point-dllmaincrtstartup"></a>기본 DLL 항목 지점 _DllMainCRTStartup  
  
Windows에서 Dll을 모두 일반적으로 라고 하는 선택적 진입점 함수를 포함할 수 있습니다 `DllMain`즉, 초기화 및 종료를 모두 호출 합니다. 이렇게 하면 할당 하거나 필요에 따라 추가 리소스를 해제할 수 있습니다. 네 가지 상황에서 진입점 함수를 호출 하는 Windows: 프로세스 연결, 프로세스 분리, 스레드 연결 및 스레드를 분리 합니다. 사용 하는 응용 프로그램을 로드 또는 응용 프로그램이 런타임에 DLL을 요청할 때 DLL 프로세스 주소 공간으로 로드 되 면 운영 체제는 별도의 DLL 데이터 복사본을 만듭니다. 이 라고 *프로세스 연결*합니다. *스레드 연결* 에서 DLL을 로드 하는 프로세스는 새 스레드를 만들 때 발생 합니다. *스레드 분리* 스레드가 종료 될 때 발생 하 고 *프로세스 분리* 는 DLL는 더 이상 필요 하 고 응용 프로그램에 의해 해제 될 때입니다. 이러한 각 이벤트를 전달에 대 한 DLL 진입점에 별도 호출을 수행 하는 운영 체제는 *이유* 각 이벤트 종류에 대 한 인수입니다. 예를 들어 운영 체제 보냅니다 `DLL_PROCESS_ATTACH` 로 *이유* 신호를 보내 프로세스 인수를 연결 합니다.  
  
호출 하는 진입점 함수를 제공 하는 VCRuntime 라이브러리 `_DllMainCRTStartup` 기본 초기화 및 종료 작업을 처리 하기. 프로세스에 연결 된 `_DllMainCRTStartup` 함수 버퍼 보안 검사를 설정, CRT 및 기타 라이브러리를 초기화, 런타임 형식 정보를 초기화 합니다, 초기화 및 정적 및 로컬이 아닌 데이터에 대 한 생성자를 호출, 스레드 로컬 저장소를 초기화 합니다 각 연결에 대 한는 내부 정적 카운터를 증가 시키고 다음 호출 하는 사용자 또는 라이브러리-제공 `DllMain`합니다. 프로세스에서 분리, 함수 반대 방향으로 이러한 단계를 거칩니다. 호출 `DllMain`, 내부 카운터를 감소 소멸자를 호출, 종료 호출 CRT 함수 등록 `atexit` 함수 및 종료의 다른 라이브러리에 알립니다. 첨부 파일 카운터가 0이 되 면 함수 반환 `FALSE` DLL을 언로드할 수는 Windows에 알립니다. `_DllMainCRTStartup` 함수 스레드 동안 호출 또한 됩니다 연결 및 스레드를 분리 합니다. 이러한 경우 VCRuntime 코드 추가 초기화 또는 자체적으로 종료 하지 않는 및 호출 `DllMain` 따라 메시지를 전달 하도록 합니다. 경우 `DllMain` 반환 `FALSE` 프로세스에서 연결 실패, 신호를 보내는 중 `_DllMainCRTStartup` 호출 `DllMain` 다시 전달 `DLL_PROCESS_DETACH` 로 *이유* 다음 나머지 인수에 통과 종료 프로세스입니다.  
  
Visual c + +에서는 기본 진입점 Dll을 빌드할 때 `_DllMainCRTStartup` 제공한 VCRuntime에 자동으로 연결 되어 있습니다. 사용 하 여 DLL에 대 한 진입점 함수를 지정할 필요가 없습니다는 [/ENTRY (진입점 기호)](../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.  
  
> [!NOTE]
> /ENTRY를 사용 하 여 DLL에 대 한 다른 진입점 함수를 지정할 수 있지만: 링커 옵션을 권장 하지는 않습니다, 모든 진입점 함수가 갖기 때문에 있는 `_DllMainCRTStartup` 동일한 순서로 않습니다. VCRuntime의 동작을 복제할 수 있도록 하는 함수를 제공 합니다. 예를 들어, 호출할 수 있습니다 [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) 즉시 프로세스에서 지원 하도록 첨부 된 [/GS (버퍼 보안 검사)](../build/reference/gs-buffer-security-check.md) 버퍼 옵션을 선택 합니다. 호출할 수 있습니다는 `_CRT_INIT` 함수를 DLL 초기화 및 종료 함수의 나머지 부분을 수행 하는 항목 지점 함수와 동일한 매개 변수를 전달 합니다.  
  
<a name="initializing-a-dll"></a>  
  
## <a name="initialize-a-dll"></a>DLL 초기화  
  
DLL에는 해당 DLL이 로드 될 때 실행 되어야 하는 초기화 코드가 있을 수 있습니다. 사용자 고유의 DLL 초기화 및 종료 기능을 수행할 수에 대 한 순서 대로 `_DllMainCRTStartup` 호출 하는 함수 호출 `DllMain` 제공할 수 있는 합니다. 프로그램 `DllMain` DLL 진입점에 필요한 서명이 있어야 합니다. 기본 진입점 함수가 `_DllMainCRTStartup` 호출 `DllMain` 동일한 매개 변수를 사용 하 여 Windows에서 전달 합니다. 기본적으로 제공 하지 않는 경우는 `DllMain` 함수, Visual c + +에서 제공 하 고에 연결 되도록 `_DllMainCRTStartup` 항상를 호출 하는 합니다. 이 DLL 초기화할 필요가 없는 경우 별도 DLL을 빌드할 때 수행할 작업을 의미 합니다.  
  
에 사용 되는 시그니처 `DllMain`:  
  
```cpp  
#include <windows.h>  
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```  
  
일부 라이브러리 래핑하는 `DllMain` 있습니다에 대 한 함수입니다. 예를 들어 기본 MFC DLL에 구현 된 `CWinApp` 개체의 `InitInstance` 및 `ExitInstance` 초기화 및 DLL에 필요한 종료를 수행 하는 멤버 함수입니다. 자세한 내용은 참조는 [MFC Dll 초기화 regular](#initializing-regular-dlls) 섹션.  
  
> [!WARNING]
> 수행할 수 있는 안전 하 게 하는 DLL 진입점에서 중요 한 제한 되어 있습니다. 참조 [유용한 일반 정보](https://msdn.microsoft.com/library/windows/desktop/dn633971#general_best_practices) 에서 호출 하는 안전 하지 않은 특정 Windows Api에 대 한 `DllMain`합니다. 하지만 필요한 경우 가장 간단한 초기화 후에 수행할 초기화 함수를 DLL에 대 한. 함수를 호출 하면 초기화 한 후 응용 프로그램을 요구할 수 있습니다 `DllMain` 가 되기 전까지 실행 및 다른 함수 DLL의에서 호출 합니다.  
  
<a name="initializing-non-mfc-dlls"></a>  
  
### <a name="initialize-ordinary-non-mfc-dlls"></a>일반 (MFC 이외) Dll 초기화  
  
VCRuntime 제공을 사용 하는 일반적인 (MFC 이외) Dll에서 직접 초기화를 수행 하려면 `_DllMainCRTStartup` 진입점 DLL 소스 코드 라고 하는 함수를 포함 해야 `DllMain`합니다. 다음 코드의 정의 보여 주는 기본 형식을 제공 `DllMain` 아래와 같습니다.  
  
```cpp  
#include <windows.h>
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason) 
    { 
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```  
  
> [!NOTE]
> 이전 Windows SDK 설명서에 따르면 하 DLL 진입점 함수의 실제 이름 링커 /ENTRY 옵션과 함께 명령줄에 지정 해야 합니다. Visual c + + 불필요 진입점 함수 이름이 /ENTRY 옵션을 사용 하려면 `DllMain`합니다. 실제로 /ENTRY 옵션 및 이름을 사용 하는 경우 프로그램 진입점 것 이외의 함수 `DllMain`, 진입점 함수가 되도록 동일한 초기화 호출 하는 지정 하지 않는 CRT 올바르게 초기화 하지 않는 `_DllMainCRTStartup` 만듭니다.  
  
<a name="initializing-regular-dlls"></a>  
  
### <a name="initialize-regular-mfc-dlls"></a>일반 MFC Dll 초기화  
  
일반 MFC Dll 때문에 `CWinApp` 개체, 초기화 및 종료 작업 MFC 응용 프로그램으로 동일한 위치에서 실행 되어야:에서 `InitInstance` 및 `ExitInstance` dll의 멤버 함수 `CWinApp`-파생 클래스입니다. MFC 제공 하기 때문에 `DllMain` 함수에서 호출 되어 `_DllMainCRTStartup` 에 대 한 `DLL_PROCESS_ATTACH` 및 `DLL_PROCESS_DETACH`를 작성 하지 말아야 직접 `DllMain` 함수입니다. MFC에서 제공 `DllMain` 함수 호출 `InitInstance` 때 DLL이 로드 및 호출 `ExitInstance` DLL 언로드되기 전에 합니다.  
  
일반 MFC DLL의 추적할 수 여러 스레드를 호출 하 여 [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) 및 [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) 에 해당 `InitInstance` 함수입니다. 이러한 함수는 스레드별 데이터를 추적 하는 DLL를 사용 합니다.  
  
동적으로 MFC에 링크를 각각, MFC 소켓 지원 또는 모든 MFC OLE, MFC 데이터베이스 또는 (DAO)를 사용 하는 경우 MFC 확장 Dll MFCO 디버그 하는 사용자가 기본 MFC DLL에서*버전*D.dll, MFCD*버전*D.dll, 및 MFCN*버전*D.dll (여기서 *버전* 버전 번호)에서 자동으로 연결 됩니다. 각 기본 MFC DLL에 사용 하는이 Dll에 대 한 다음 미리 정의 된 초기화 함수 중 하나를 호출 해야 `CWinApp::InitInstance`합니다.  
  
|MFC 지원 유형|호출할 초기화 함수|  
|-------------------------|-------------------------------------|  
|MFC OLE (MFCO*버전*D.dll)|`AfxOleInitModule`|  
|MFC 데이터베이스 (MFCD*버전*D.dll)|`AfxDbInitModule`|  
|MFC 소켓 (MFCN*버전*D.dll)|`AfxNetInitModule`|  
  
<a name="initializing-extension-dlls"></a>  
  
### <a name="initialize-mfc-extension-dlls"></a>MFC 확장명 Dll 초기화  
  
MFC 확장 Dll에는 없으므로 `CWinApp`-파생 된 (기본 MFC Dll 수행 됨) 처럼 개체를 초기화 및 종료 코드를 추가 해야는 `DllMain` MFC DLL 마법사에서 생성 하는 함수입니다.  
  
 마법사는 MFC 확장 Dll에 대 한 다음 코드를 제공합니다. 코드에서 `PROJNAME` 자리 표시자 프로젝트의 이름입니다.  
  
```cpp  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // MFC extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
새 `CDynLinkLibrary` 개체 초기화 하는 동안에 MFC 확장 DLL을 내보낼 수 있습니다. `CRuntimeClass` 개체 또는 클라이언트 응용 프로그램에는 리소스입니다.  
  
MFC 확장 DLL에서 하나 이상의 기본 MFC Dll을 사용 하도록 하려는 경우 초기화 함수를 만드는 내보내야는 `CDynLinkLibrary` 개체입니다. 해당 함수는 각각의 MFC 확장 DLL을 사용 하는 일반 MFC Dll에서 호출 되어야 합니다. 이 초기화 함수를 호출 하는 적절 한 장소는 `InitInstance` 기본 MFC DLL의 멤버 함수 `CWinApp`-MFC 확장 DLL의 내보낸된 클래스 또는 함수 중 하나를 사용 하기 전에 개체를 파생 합니다.  
  
에 `DllMain` 를 MFC DLL 마법사 생성에 대 한 호출 `AfxInitExtensionModule` 모듈의 런타임 클래스를 캡처합니다 (`CRuntimeClass` 구조)의 개체 팩터리 뿐만 아니라 (`COleObjectFactory` 개체)에 대 한 때를 사용할는 `CDynLinkLibrary` 개체가 만들어집니다. 반환 값을 확인 해야 `AfxInitExtensionModule`값이 0에서 반환 되 면; `AfxInitExtensionModule`에서 0을 반환 하면 `DllMain` 함수.  
  
MFC 확장 DLL에 실행 파일에 명시적으로 연결 되는 경우 (호출 하면 실행 파일을 의미 `AfxLoadLibrary` DLL에 연결 하 여)에 대 한 호출을 추가 해야 `AfxTermExtensionModule` 에 `DLL_PROCESS_DETACH`합니다. 이 함수에서는 각 프로세스 MFC 확장 DLL에서에서 분리할 때 MFC 확장 DLL 정리 하는 MFC (때나의 결과로 DLL이 언로드되어 프로세스가 종료 될 때 발생 하는 `AfxFreeLibrary` 호출). MFC 확장 DLL 응용 프로그램에 대 한 호출에 암시적으로 연결 되는 경우 `AfxTermExtensionModule` 필요 하지 않습니다.  
  
MFC 확장 Dll에 링크 명시적으로 호출 해야 하는 응용 프로그램 `AfxTermExtensionModule` DLL을 해제 하는 경우. 또한 사용 해야 `AfxLoadLibrary` 및 `AfxFreeLibrary` (Win32 함수 대신 `LoadLibrary` 및 `FreeLibrary`) 응용 프로그램은 여러 스레드를 사용 하는 경우. 사용 하 여 `AfxLoadLibrary` 및 `AfxFreeLibrary` MFC 확장 DLL이 로드 되거나 언로드될 전역 MFC 상태가 손상 되지 않는 경우 실행 하는 시작 및 종료 코드가 있는지 확인 합니다.  
  
MFCx0.dll 시간순으로 완전히 초기화 되기 때문에 `DllMain` 은 호출 메모리를 할당할 수 있고 MFC 함수 내에서 호출할 `DllMain` (달리 MFC의 16 비트 버전).  
  
확장 Dll를 처리할 수 처리 하 여 다중 스레딩는 `DLL_THREAD_ATTACH` 및 `DLL_THREAD_DETACH` 의 경우에 `DllMain` 함수입니다. 이러한 경우에 전달 되 `DllMain` 스레드 연결 시점과 DLL에서 분리 합니다. 호출 [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) 스레드 로컬 저장소 (TLS) DLL에 연결 된 모든 스레드에 대 한 인덱스를 유지 하기 위해 DLL을 사용 하면 DLL이 연결 합니다.  
  
Afxdllx.h 헤더 파일에는 정의 대 한 같은 MFC 확장 Dll에서 사용 되는 구조에 대 한 특수 정의 `AFX_EXTENSION_MODULE` 및 `CDynLinkLibrary`합니다. MFC 확장 DLL에에서이 헤더 파일을 포함 해야 합니다.  
  
> [!NOTE]
>  반드시 정의 아니고 정의 하는 `_AFX_NO_XXX` Stdafx.h에는 매크로입니다. 이러한 매크로 여부는 특정 대상 플랫폼 기능을 지원 하는지 여부를 확인 하는 용도만 존재 합니다. 이러한 매크로 확인 하 여 프로그램을 작성할 수 있습니다 (예를 들어 `#ifndef _AFX_NO_OLE_SUPPORT`), 프로그램 정의 하거나 이러한 매크로 정의 해제할 안 되지만 합니다.  
  
다중 스레딩 핸들에 포함 된 샘플 초기화 함수 [를 사용 하 여 스레드 로컬 저장소에 동적 연결 라이브러리](http://msdn.microsoft.com/library/windows/desktop/ms686997) Windows sdk에서입니다. 이 샘플에 진입점 함수가 포함 되어 있는지 참고 `LibMain`,이 함수 이름을 지정 해야 하지만 `DllMain` MFC 및 C 런타임 라이브러리와 함께 작동 하도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
  
[Visual C++의 DLL](../build/dlls-in-visual-cpp.md)  
[DllMain 진입점](https://msdn.microsoft.com/library/windows/desktop/ms682583.aspx)  
[동적 연결 라이브러리에 대 한 유용한 정보](https://msdn.microsoft.com/library/windows/desktop/dn633971.aspx)  