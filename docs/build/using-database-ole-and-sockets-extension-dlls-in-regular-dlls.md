---
title: "기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 확장"
  - "DLL[C++], 초기화"
  - "DLL[C++], 기본"
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 DLL에서 확장 DLL을 사용하는 경우, 확장 DLL이 기본 DLL의 **CDynLinkLibrary** 개체 체인에 연결되어 있지 않으면 이와 관련된 문제가 하나 이상 발생할 수 있습니다.  MFC 데이터베이스, OLE 및 소켓 지원 DLL의 디버그 버전은 확장 DLL로 구현되기 때문에, 이러한 MFC 기능을 사용하는 경우에는 사용자의 확장 DLL을 명시적으로 사용하지 않아도 이와 유사한 문제가 발생할 수 있습니다.  이러한 문제는 다음과 같습니다.  
  
-   확장 DLL에정의된 클래스 형식의 개체를 deserialize하려고 하면 "경고: 보관 저장소에서 CYourClass를 로드할 수 없습니다.  클래스가 정의되지 않았습니다."라는 메시지가 TRACE 디버그 창에 나타나고 개체를 serialize할 수 없습니다.  
  
-   잘못된 클래스임을 나타내는 예외가 throw됩니다.  
  
-   `AfxFindResourceHandle`이 **NULL** 또는 올바르지 않은 리소스 핸들을 반환하기 때문에 확장 DLL에 저장된 리소스를 로드할 수 없습니다.  
  
-   `DllGetClassObject`, `DllCanUnloadNow`와 `COleObjectFactory`의 멤버 함수인 `UpdateRegistry`, `Revoke`, `RevokeAll` 및 `RegisterAll`이 확장 DLL에 정의된 클래스 팩터리를 찾지 못합니다.  
  
-   `AfxDoForAllClasses`가 확장 DLL의 모든 클래스에 대해서 작동하지 않습니다.  
  
-   표준 MFC 데이터베이스, 소켓 또는 OLE 리소스가 로드되지 않습니다.  예를 들어, 기본 DLL이 MFC 데이터베이스 클래스를 올바르게 사용하고 있는 경우에도 **AfxLoadString**\(**AFX\_IDP\_SQL\_CONNECT\_FAIL**\)이 빈 문자열을 반환합니다.  
  
 이러한 문제를 해결하려면 **CDynLinkLibrary** 개체를 만드는 확장 DLL에서 초기화 함수를 만들고 내보냅니다.  이 초기화 함수는 해당 확장 DLL을 사용하는 각 기본 DLL에서 한 번만 호출됩니다.  
  
## MFC OLE, MFC 데이터베이스\(또는 DAO\) 또는 MFC 소켓 지원  
 기본 DLL에서 MFC OLE, MFC 데이터베이스\(또는 DAO\) 또는 MFC 소켓을 지원하는 경우에는 각각 MFC 디버그 확장 DLL인 MFCOxxD.dll, MFCDxxD.dll 및 MFCNxxD.dll\(xx는 버전 번호\)이 자동으로 링크됩니다.  사용자는 사용 중인 각 DLL에 대해 미리 정의된 초기화 함수를 호출해야 합니다.  
  
 데이터베이스가 지원되는 경우에는 `AfxDbInitModule` 호출을 기본 DLL의 `CWinApp::InitInstance` 함수에 추가합니다.  이 호출은 기본 클래스 호출이나 MFCDxxD.dll에 액세스하는 추가 코드 앞에 위치해야 합니다.  이 함수는 매개 변수를 사용하지 않으며 void를 반환합니다.  
  
 OLE 지원을 사용하는 경우에는 `AfxOleInitModule` 호출을 기본 DLL의 `CWinApp::InitInstance` 함수에 추가합니다.  **COleControlModule InitInstance** 함수가 `AfxOleInitModule`을 이미 호출했을 수도 있으므로 OLE 컨트롤을 빌드하고 `COleControlModule`을 사용하는 경우에는 이러한 `AfxOleInitModule` 호출을 추가할 필요가 없습니다.  
  
 소켓 지원을 사용하는 경우에는 `AfxNetInitModule` 호출을 기본 DLL의 `CWinApp::InitInstance` 함수에 추가합니다.  
  
 MFC DLL 및 응용 프로그램의 릴리스 빌드에서는 데이터베이스, 소켓 또는 OLE 지원을 위해 별도의 DLL을 사용하지 않습니다.  그러나 릴리스 모드에서는 이 초기화 함수를 호출하는 것이 안전합니다.  
  
## CDynLinkLibrary 개체  
 이 항목의 처음 부분에 언급한 각 작업을 수행하는 동안 MFC에서 필요한 값 또는 개체를 검색해야 합니다.  예를 들어, deserialization을 수행하는 동안 MFC에서 현재 사용 가능한 모든 런타임 클래스를 검색하여 보관 저장소에 있는 개체를 해당 개체의 올바른 런타임 클래스와 일치시켜야 합니다.  
  
 이러한 검색 과정의 일부로 MFC에서는 **CDynLinkLibrary** 개체 체인을 차례대로 이동하여 사용되는 모든 확장 DLL을 검색합니다.  **CDynLinkLibrary** 개체는 생성될 때 자동으로 체인에 연결되며 초기화 시 각 확장 DLL에 의해 차례대로 만들어집니다.  또한 모든 모듈\(응용 프로그램 또는 기본 DLL\)에는 자체의 **CDynLinkLibrary** 개체 체인이 있습니다.  
  
 확장 DLL을 **CDynLinkLibrary** 체인에 연결하기 위해 확장 DLL을 사용하는 모든 모듈의 컨텍스트에서 **CDynLinkLibrary** 개체를 만들어야 합니다.  따라서 기본 DLL에서 확장 DLL을 사용하면 해당 확장 DLL에서 **CDynLinkLibrary** 개체를 만드는 초기화 함수를 내보내야 합니다.  또한 이렇게 내보내진 초기화 함수는 확장 DLL을 사용하는 모든 기본 DLL에서 호출되어야 합니다.  
  
 확장 DLL을 MFC 응용 프로그램\(.exe\)에서만 사용하고 기본 DLL에서는 사용하지 않으려면 확장 DLL의 `DllMain` 함수에서 **CDynLinkLibrary** 개체를 만듭니다.  이 작업은 MFC DLL 마법사의 확장 DLL 코드에서 수행됩니다.  확장 DLL을 암시적으로 로드하는 경우, `DllMain`은 응용 프로그램이 시작되기 전에 로드되고 실행됩니다.  생성된 모든 **CDynLinkLibrary**는 MFC DLL이 MFC 응용 프로그램을 위해 예약한 기본 체인에 연결됩니다.  
  
 특히, 확장 DLL이 메모리에서 동적으로 언로드되는 경우, 하나의 확장 DLL에서 여러 개의 **CDynLinkLibrary** 개체가 하나의 체인에 연결되는 것은 좋지 않습니다.  초기화 함수는 모든 모듈에서 한 번만 호출해야 합니다.  
  
## 샘플 코드  
 이 샘플 코드에서는 기본 DLL이 확장 DLL에 암시적으로 링크하는 것으로 가정합니다.  이 작업은 기본 DLL을 빌드할 때 확장 DLL의 가져오기 라이브러리\(.lib\)에 링크함으로써 수행됩니다.  
  
 확장 DLL의 소스에 다음 줄이 포함되어야 합니다.  
  
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
        // extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 **InitYourExtDLL** 함수는 내보내야 합니다.  **\_\_declspec\(dllexport\)**을 사용하거나 해당 DLL의 .def 파일에 다음 줄을 추가하면 이 함수를 내보낼 수 있습니다.  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 다음과 같이 확장 DLL을 사용할 각 기본 DLL에서 `CWinApp` 파생 개체의 `InitInstance` 멤버에 대한 호출을 추가합니다.  
  
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
    TRACE0("YOUR regular DLL initializing\n");  
  
    // wire any extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### 수행할 작업  
  
-   [확장 DLL 초기화](../build/initializing-extension-dlls.md)  
  
-   [기본 DLL 초기화](../build/initializing-regular-dlls.md)  
  
### 추가 정보  
  
-   [확장 DLL](../build/extension-dlls.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
  
## 참고 항목  
 [확장 DLL](../build/extension-dlls.md)