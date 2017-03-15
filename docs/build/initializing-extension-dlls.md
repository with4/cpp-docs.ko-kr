---
title: "확장 DLL 초기화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "확장 DLL[C++], 초기화"
  - "DLL 초기화"
ms.assetid: 08ad0381-3808-4bea-a93c-c9ba62496543
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 확장 DLL 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

확장 DLL에는 기본 DLL과 달리 `CWinApp` 파생 개체가 없기 때문에 MFC DLL 마법사가 생성하는 `DllMain` 함수에 초기화 및 종료 코드를 사용자가 직접 추가해야 합니다.  
  
 MFC DLL 마법사에서는 확장 DLL에 대해 다음과 같은 코드를 제공합니다.  아래 코드에서 `PROJNAME`은 사용자의 프로젝트 이름에 대한 자리 표시자입니다.  
  
```  
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
  
      // Extension DLL one-time initialization  
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
  
 초기화하는 동안 새 **CDynLinkLibrary** 개체를 만들면 확장 DLL이 `CRuntimeClass` 개체 또는 리소스를 클라이언트 응용 프로그램에 내보낼 수 있습니다.  
  
 하나 이상의 기본 DLL에서 확장 DLL을 사용하려면 **CDynLinkLibrary** 개체를 만드는 초기화 함수를 내보내야 합니다.  이 함수는 확장 DLL을 사용하는 각각의 기본 DLL에서 호출되어야 합니다.  이 초기화 함수는 확장 DLL의 내보내는 클래스 또는 함수를 사용하기 전에 기본 DLL에 포함된 `CWinApp` 파생 개체의 `InitInstance` 멤버 함수에서 호출하는 것이 좋습니다.  
  
 MFC DLL 마법사가 생성하는 `DllMain`에서 `AfxInitExtensionModule`을 호출하면 **CDynLinkLibrary** 개체가 만들어질 때 사용할 해당 개체 팩터리\(`COleObjectFactory` 개체\)와 해당 모듈의 런타임 클래스\(`CRuntimeClass` 구조체\)가 캡처됩니다.  이 때 `AfxInitExtensionModule`의 반환 값을 확인하여 `AfxInitExtensionModule`에서 0이 반환되면 `DllMain` 함수에서 0을 반환해야 합니다.  
  
 확장 DLL이 실행 파일에 명시적으로 링크되는 경우 즉, 실행 파일이 `AfxLoadLibrary`를 호출하여 해당 DLL에 링크하는 경우에는 `AfxTermExtensionModule`에 대한 호출을 **DLL\_PROCESS\_DETACH**에 추가해야 합니다.  이 함수를 사용하면 프로세스가 종료되거나 `AfxFreeLibrary` 호출 결과로 DLL이 언로드되어 각 프로세스가 확장 DLL에서 분리될 때 MFC에서 해당 확장 DLL을 정리합니다.  확장 DLL이 응용 프로그램에 암시적으로 링크되는 경우에는 `AfxTermExtensionModule`을 호출하지 않아도 됩니다.  
  
 확장 DLL에 명시적으로 링크하는 응용 프로그램은 DLL을 해제할 때 **AfxTermExtensionModule**을 호출해야 합니다.  또한 다중 스레드를 사용하는 응용 프로그램의 경우에는 Win32 함수인 **LoadLibrary** 및 **FreeLibrary** 대신 `AfxLoadLibrary` 및 `AfxFreeLibrary`를 사용해야 합니다.  `AfxLoadLibrary` 및 `AfxFreeLibrary`를 사용하면 확장 DLL이 로드되거나 언로드될 때 실행되는 시작 코드와 종료 코드가 전역 MFC 상태를 손상시키지 않게 됩니다.  
  
 MFCx0.dll은 `DllMain`이 호출될 때 완전히 초기화되므로 16비트 버전의 MFC와는 달리 `DllMain` 내에서 메모리를 할당하고 MFC 함수를 호출할 수 있습니다.  
  
 확장 DLL은 `DllMain` 함수에서 **DLL\_THREAD\_ATTACH** 및 **DLL\_THREAD\_DETACH**의 경우를 처리하여 다중 스레드를 관리합니다.  이러한 경우는 스레드가 DLL에서 연결되거나 분리될 때 `DllMain`에 전달됩니다.  DLL을 연결할 때 [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801)를 호출하면 DLL은 해당 DLL에 연결된 모든 스레드에 대해 TLS\(스레드 로컬 저장소\) 인덱스를 유지합니다.  
  
 헤더 파일 Afxdllx.h에는 `AFX_EXTENSION_MODULE`, **CDynLinkLibrary** 등의 확장 DLL에서 사용되는 구조체가 정의됩니다.  확장 DLL에는 이 헤더 파일을 포함시켜야 합니다.  
  
> [!NOTE]
>  Stdafx.h에 있는 모든 \_AFX\_NO\_XXX 매크로에 대해서 정의하거나 정의를 해제하지 않아야 합니다.  자세한 내용은 기술 자료 문서의 "PRB: \_AFX\_NO\_XXX 정의 때 문제가 발생한다"\(Q140751\)를 참조하십시오.  [http:\/\/search.support.microsoft.com\/](http://search.support.microsoft.com/) 또는 MSDN 라이브러리에서 기술 자료 문서를 찾을 수 있습니다.  
  
 다중 스레딩을 처리하는 샘플 초기화 함수는 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Using Thread Local Storage in a Dynamic\-Link Library](http://msdn.microsoft.com/library/windows/desktop/ms686997)에 포함되어 있습니다.  이 샘플에는 **LibMain**이라는 진입점 함수가 포함되어 있지만 이 함수가 MFC 및 C 런타임 라이브러리와 함께 작동하도록 하려면 이 함수 이름을 `DllMain`으로 변경해야 합니다.  
  
 MFC 샘플 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90)에서는 초기화 함수의 사용 방법을 보여 줍니다.  
  
## 수행할 작업  
  
-   [기본 DLL 초기화](../build/initializing-regular-dlls.md)  
  
-   [비 MFC DLL 초기화](../build/initializing-non-mfc-dlls.md)  
  
## 추가 정보  
  
-   [C 런타임 라이브러리 동작 및 \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt34" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>The function specification for DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt35" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic\-link library entry\-point function\(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## 참고 항목  
 [DLL 초기화](../build/initializing-a-dll.md)