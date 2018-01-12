---
title: "기본 MFC Dll에서 데이터베이스, OLE 및 소켓 MFC 확장 Dll을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0042dd5dc6049447868cf5ca5ea1112b3695f3a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>기본 MFC Dll에서 데이터베이스, OLE 및 소켓 MFC 확장명 Dll 사용
MFC 확장 DLL 연결 되어 있지 않습니다에 MFC 확장 DLL 기본 MFC DLL에서 사용 하는 경우는 **CDynLinkLibrary** 체인 개체 기본 MFC dll에 일련의 관련된 문제를 하나 이상에 실행할 수 있습니다. MFC 데이터베이스, OLE 및 소켓의 디버그 버전을 지원 하기 때문에 Dll이 MFC 확장 Dll로 구현 됩니다, 그리고 사용자의 MFC 확장 Dll 명시적으로 사용 하지 않아도 하는 경우에 이러한 MFC를 사용 하는 경우 비슷한 문제가 기능 발생할 수 있습니다. 이러한 문제는:  
  
-   때 MFC 확장 DLL 메시지에에서 정의 된 클래스 형식의 개체를 deserialize 하려고 했습니다. "경고: CYourClass 보관 파일에서 로드할 수 없습니다. 클래스 정의 되지 않았습니다. " 추적 디버그 창 및 개체에 serialize 하는 데 실패 하면 나타납니다.  
  
-   잘못 된 클래스를 나타내는 예외가 throw 될 수 있습니다.  
  
-   MFC 확장 DLL에에서 저장 된 리소스 때문에 로드 되지 `AfxFindResourceHandle` 반환 **NULL** 또는 잘못 된 리소스 핸들입니다.  
  
-   `DllGetClassObject``DllCanUnloadNow`, 및 `UpdateRegistry`, `Revoke`, `RevokeAll`, 및 `RegisterAll` 의 멤버 함수 `COleObjectFactory` MFC 확장 DLL에에서 정의 된 클래스 팩터리를 찾지 못합니다.  
  
-   `AfxDoForAllClasses`모든 클래스는 MFC 확장 DLL에에서 대해서는 작동 하지 않습니다.  
  
-   표준 MFC 데이터베이스, 소켓 또는 / / OLE 리소스 로드 하지 못했습니다. 예를 들어 **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) 기본 MFC DLL은 MFC 데이터베이스 클래스를 사용 하 여 제대로 하는 경우에 빈 문자열을 반환 합니다.  
  
 이러한 문제에 솔루션을 만들고 MFC 확장 DLL 만드는에 초기화 함수를 내보내려면은 한 **CDynLinkLibrary** 개체입니다. 각 기본 MFC DLL에서 MFC 확장 DLL을 사용 하는 정확히 한 번이 초기화 함수를 호출 합니다.  
  
## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC 데이터베이스 (또는 DAO) 또는 MFC 소켓 지원  
 모든 MFC OLE, MFC 데이터베이스 또는 (DAO)를 사용 하는 각각 기본 MFC DLL에서 MFC 소켓 지원, MFC 디버그 MFC 확장 Dll MFCOxxD.dll, MFCDxxD.dll, 및 MFCNxxD.dll (여기서 xx는 버전 번호) 자동으로 연결 됩니다. 각 사용 중인이 Dll에 대 한 미리 정의 된 초기화 함수를 호출 해야 합니다.  
  
 데이터베이스 지원에 대 한 호출을 추가 `AfxDbInitModule` 일반 MFC DLL에 `CWinApp::InitInstance` 함수입니다. 이 호출은 기본 클래스 호출이 나 추가 MFCDxxD.dll에 액세스 하는 코드에 있는지 확인 합니다. 이 함수는 매개 변수를 사용 하 고 void를 반환 합니다.  
  
 OLE 지원에 대 한 호출을 추가 `AfxOleInitModule` 일반 MFC DLL에 `CWinApp::InitInstance`합니다. **COleControlModule InitInstance** 함수 호출 `AfxOleInitModule` 이미 사용 하 고 OLE 컨트롤을 작성 하는 경우 `COleControlModule`,이 호출을 추가 하지 말아야 `AfxOleInitModule`합니다.  
  
 소켓 지원에 대 한 호출을 추가 `AfxNetInitModule` 일반 MFC DLL에 `CWinApp::InitInstance`합니다.  
  
 Note는 MFC Dll의 릴리스 빌드를 및 응용 프로그램 데이터베이스, 소켓에 대 한 별도 Dll를 사용 하지 않거나 OLE를 지원 합니다. 그러나 릴리스 모드의 이러한 초기화 함수를 호출 해도 안전 합니다.  
  
## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary 개체가  
 각이 항목의 앞부분에 언급 한 작업 중 MFC를 원하는 값 이나 개체를 검색 해야 합니다. 예를 들어 deserialization을 수행 하는 동안 MFC의 적절 한 런타임 클래스와 함께 보관 파일에는 개체와 일치 하도록 모든 현재 사용할 수 있는 런타임 클래스를 검색 해야 합니다.  
  
 이러한 검색의 일부로 MFC를 통해 검색 모든 MFC 확장 Dll 사용에서의 체인을 탐색 하 여 **CDynLinkLibrary** 개체입니다. **CDynLinkLibrary** 개체의 생성 되는 동안 체인에 자동으로 연결 하 고 초기화 하는 동안에 각 MFC 확장 DLL에 의해 생성 됩니다. 또한 모든 모듈 (응용 프로그램 또는 일반 MFC DLL)에의 한 체인과 **CDynLinkLibrary** 개체입니다.  
  
 MFC 확장 DLL에 유선 가져오기에 대 한는 **CDynLinkLibrary** 만들어야 하 체인은 **CDynLinkLibrary** MFC 확장 DLL을 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. 따라서 MFC 확장 DLL 기본 MFC Dll에서 사용할 것인지, 하는 경우는 내보낸된 초기화를 만드는 함수를 제공 해야는 **CDynLinkLibrary** 개체입니다. MFC 확장을 사용 하는 모든 기본 MFC DLL DLL 내보낸된 초기화 함수를 호출 해야 합니다.  
  
 MFC 확장 DLL에서 MFC 응용 프로그램 (.exe) 및 기본 MFC DLL에서 하지 사용할 예정일 뿐 이라고 경우 만들기에 충분는 **CDynLinkLibrary** MFC 확장 DLL에의 한 개체 `DllMain`합니다. MFC DLL 마법사 MFC 확장 DLL 코드에서 수행 하는 작업입니다. 암시적으로 MFC 확장 DLL을 로드할 때 `DllMain` 로드 하 고 응용 프로그램이 시작 되기 전에 실행 됩니다. 모든 **CDynLinkLibrary** 만들기 MFC DLL이 MFC 응용 프로그램에 대 한 예약 하는 기본 체인에 다음과 같은 합니다.  
  
 여러 개 바람직하지는 **CDynLinkLibrary** 개체는 하나의 체인의 한 MFC 확장 DLL에서에서 특히 MFC 확장 DLL을 메모리에서 동적으로 로드 됩니다. 모든 모듈에서 초기화 함수가 두 번 이상는 호출 하지 마십시오.  
  
## <a name="sample-code"></a>샘플 코드  
 이 샘플 코드에서는 기본 MFC DLL이 MFC 확장 DLL에 암시적으로 링크를 가정 합니다. 이 기본 MFC DLL을 빌드할 때 MFC 확장 DLL 가져오기 라이브러리 (.lib)에 연결 하 여 수행 됩니다.  
  
 다음 줄은 MFC 확장 DLL의 소스 여야 합니다.  
  
```  
// YourExtDLL.cpp:  
  
// standard MFC extension DLL routines  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
    if (dwReason == DLL_PROCESS_ATTACH)  
    {  
        // MFC extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular MFC DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 에 가져올 수는 **InitYourExtDLL** 함수입니다. 수행할 수 있습니다 사용 하 여 **__declspec (dllexport)** 또는 다음과 같이 DLL의.def 파일에:  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 에 대 한 호출 추가 `InitInstance` 의 멤버는 `CWinApp`-파생 MFC 확장 DLL을 사용 하 여 각 기본 MFC DLL에 대 한 개체:  
  
```  
// YourRegularDLL.cpp:  
  
class CYourRegularDLL : public CWinApp  
{  
public:  
    virtual BOOL InitInstance(); // Initialization  
    virtual int ExitInstance();  // Termination  
  
    // nothing special for the constructor  
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }  
};  
  
BOOL CYourRegularDLL::InitInstance()  
{  
    // any DLL initialization goes here  
    TRACE0("YOUR regular MFC DLL initializing\n");  
  
    // wire any MFC extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [MFC 확장 DLL 초기화](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
-   [일반 MFC Dll 초기화](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [MFC 확장명 DLL](../build/extension-dlls.md)  
  
-   [정적으로 MFC에 링크된 기본 MFC DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크된 기본 MFC DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 확장명 DLL](../build/extension-dlls.md)