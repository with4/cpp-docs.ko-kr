---
title: "확장 Dll | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afxdll
dev_langs: C++
helpviewer_keywords:
- memory [C++], DLLs
- MFC extension DLLs [C++]
- AFXDLL library
- shared resources [C++]
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- resource sharing [C++]
- extension DLLs [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45e94997dbeb2c6413ffcdc1272a3a46a7e220ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-extension-dlls"></a>MFC 확장명 Dll
MFC 확장 DLL은 일반적으로 기존의 Microsoft Foundation Class 라이브러리 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 DLL입니다.  
  
 MFC 확장 DLL은 다음 기능 및 요구 사항에 있습니다.  
  
-   클라이언트 실행 파일을 컴파일하면 MFC 응용 프로그램 이어야 합니다 `_AFXDLL` 정의 합니다.  
  
-   동적으로 MFC에 링크 하는 MFC 기본 DLL에서 MFC 확장 DLL을 사용할 수도 있습니다.  
  
-   MFC 확장명 Dll 사용 컴파일해야 `_AFXEXT` 정의 합니다. 이렇게 하면 `_AFXDLL` 도 정의 MFC 헤더 파일에서 적절 한 선언 끌어온 있는지 확인 합니다. 또한 `AFX_EXT_CLASS` 로 정의 `__declspec(dllexport)` DLL을 작성 하는 동안 있는 MFC 확장 DLL에에서 클래스를 선언 하려면이 매크로 사용 하는 경우 필요 합니다.  
  
-   MFC 확장 Dll에서 파생 된 클래스를 인스턴스화하면 안 `CWinApp`, 있지만이 개체를 제공 하는 클라이언트 응용 프로그램 (또는 DLL)에 의존 해야 합니다.  
  
-   하지만 MFC 확장명 Dll은 있어야 제공 된 `DllMain` 작동 하 고 필요한 초기화를 수행 합니다.  
  
 확장 Dll은 MFC (MFC 공유 버전 라고도 함)의 동적 연결 라이브러리 버전을 사용 하 여 작성 됩니다. 만 MFC 실행 파일 (응용 프로그램 또는 일반 MFC Dll)의 MFC 공유 버전으로 작성 하는 MFC 확장 DLL을 사용할 수 있습니다. 클라이언트 응용 프로그램 및 MFC 확장 DLL 모두 같은 버전의 MFCx0.dll 사용 해야 합니다. MFC 확장 DLL MFC에서 새로운 사용자 지정 클래스를 파생 시킨 수 있으며 다음이 확장 된 버전의 MFC DLL을 호출 하는 응용 프로그램을 제공할 수 있습니다.  
  
 응용 프로그램과 DLL 사이의 MFC 파생 개체를 전달 하기 위한 확장 Dll은 사용할 수도 있습니다. 전달된 된 개체와 연결 된 멤버 함수는 개체가 생성 된 모듈에 있습니다. 이러한 함수는 내보내지므로 제대로 mfc 공유 DLL 버전을 사용 하는 경우, MFC 자유롭게 전달할 수 있습니다 또는 MFC에서 파생 된 개체 포인터 응용 프로그램과 MFC 확장 Dll 로드 합니다.  
  
 MFC 확장 DLL 공유 버전의 MFC 사용 하 여 같은 방식으로 응용 프로그램의 MFC 공유 DLL 버전을 사용 하 여 몇 가지 사항을 추가로 고려해 야 합니다.  
  
-   에 없는 한 `CWinApp`-파생 된 개체입니다. 으로 작업 해야는 `CWinApp`-클라이언트 응용 프로그램의 개체를 파생 합니다. 이 클라이언트 응용 프로그램 기본 메시지 펌프, 유휴 상태 루프 및 등을 소유 함을 의미 합니다.  
  
-   호출 `AfxInitExtensionModule` 에 해당 `DllMain` 함수입니다. 이 함수의 반환 값을 검사 해야 합니다. 값이 0에서 반환 되 면 `AfxInitExtensionModule`에서 0을 반환 하면 `DllMain` 함수입니다.  
  
-   만듭니다는 **CDynLinkLibrary** 하고자 할 경우 MFC 확장 DLL 내보내기 초기화 하는 동안 개체 `CRuntimeClass` 개체 또는 응용 프로그램에는 리소스입니다.  
  
 MFC의 4.0 버전 이전 DLL이이 유형의 AFXDLL 호출 되었습니다. AFXDLL 참조 하는 `_AFXDLL` DLL을 빌드할 때 정의 된 전처리기 기호입니다.  
  
 에 설명 된 규칙에 따라 공유 버전의 MFC에 대 한 가져오기 라이브러리 이름을 [MFC Dll에 대 한 명명 규칙](../build/naming-conventions-for-mfc-dlls.md)합니다. Visual c + + MFC Dll 및의 비 MFC Dll를 사용 하 고 응용 프로그램과 함께 배포할 수 있는 많은 미리 작성 된 버전을 제공 합니다. 이러한 Redist.txt Program Files\Microsoft Visual Studio 폴더에 설치 되는 설명 되어 있습니다.  
  
 .Def 파일을 내보내는 경우 헤더 파일의 시작과 끝에 다음 코드를 추가 합니다.  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 이 네 줄 MFC 확장 DLL에 대 한 코드가 올바르게 컴파일 했는지 확인 합니다. 이 네 개의 줄 컴파일 또는 올바르게 연결 DLL 발생할 수 있습니다.  
  
 MFC를 전달 해야 할 경우 MFC DLL은 DLL에서 MFC에서 파생 된 개체 포인터는 MFC 확장 DLL 이어야 합니다. 전달된 된 개체와 연결 된 멤버 함수는 개체가 생성 된 모듈에 있습니다. 이러한 함수는 내보내지므로 제대로 mfc 공유 DLL 버전을 사용 하는 경우, MFC 자유롭게 전달할 수 있습니다 또는 MFC에서 파생 된 개체 포인터 응용 프로그램과 MFC 확장 Dll 로드 합니다.  
  
 C + + 이름 관리 및 내보내기 문제로 인해는 내보내기 목록에서 MFC 확장 DLL 수도 있습니다 마다 다를 수 동일한 DLL의 디버그 버전과 소매 다양 한 플랫폼에 대 한 합니다. 소매 MFCx0.dll에 약 2, 000 내보낸 진입점이 있습니다. 디버그 MFCx0D.dll 약 3000 내보낸된 진입점에 있습니다.  
  
## <a name="memory-management"></a>메모리 관리  
 MFCx0.dll 및 모든 MFC 확장 Dll 클라이언트 응용 프로그램의 주소 공간에 로드 사용 하 여 동일한 메모리 할당자, 리소스 로드 및 기타 MFC 전역 상태 동일한 응용 프로그램에서 듯. 이 기능은 기본 MFC Dll과 비 MFC DLL 라이브러리는 정반대 작업을 수행 하 고 각 DLL이 프로그램은 자체 메모리 풀에서 할당 하도록 하기 때문에 중요 합니다.  
  
 MFC 확장 DLL이 메모리를 할당 하는 경우 해당 메모리가 다른 응용 프로그램 할당 된 개체와 자유롭게 혼합 될 수 있습니다. 또한 동적으로 MFC에 링크는 응용 프로그램이 실패할 경우 보호는 운영 체제의 해당 DLL을 공유 하는 다른 MFC 응용 프로그램의 무결성을 유지 합니다.  
  
 마찬가지로 다른 전역 MFC 상태는 리소스를 로드 하 여 현재 실행 파일과 같은 클라이언트 응용 프로그램 및 모든 MFC 확장 Dll mfcx0.dll 자체 간에 공유 됩니다.  
  
## <a name="sharing-resources-and-classes"></a>공유 리소스 및 클래스  
 리소스 내보내기 리소스 목록을 통해 수행 됩니다. 각 응용 프로그램에 단일 연결된 목록이 포함 되어 **CDynLinkLibrary** 개체입니다. 대부분의 리소스를 로드 하는 표준 MFC 구현에서는 현재 리소스 모듈에서 먼저 찾습니다 리소스를 찾을 때는 (`AfxGetResourceHandle`) 리소스가 없는 경우의 목록으로 이동 **CDynLinkLibrary** 개체 요청된 된 리소스를 로드 하려고 합니다.  
  
 목록 트래버스 단점이 약간 느려질 것 및 리소스 ID 범위 관리를 필요로 합니다. MFC 확장 Dll이 몇 개에 연결 하는 클라이언트 응용 프로그램 DLL 인스턴스 핸들을 지정 하지 않고도 DLL에서 제공 하는 리소스를 사용할 수 있다는 이점이 있습니다. `AfxFindResourceHandle`API는 순환 리소스 목록에 대 한 지정 된 일치 하는 합니다. 이름 및 리소스의 형식을 사용 해야 하 고 처음 발견 되는 리소스 핸들 (또는 NULL)를 반환 합니다.  
  
 목록으로 이동 하 여만 특정 위치에서 리소스를 로드 하지 않으려면 함수를 사용 `AfxGetResourceHandle` 및 `AfxSetResourceHandle` 하 기존 핸들을 저장 하 고 새 핸들을 설정 합니다. 클라이언트 응용 프로그램에 반환 하기 전에 이전 리소스 핸들을 복원 해야 합니다. 메뉴를 명시적으로 로드 하려면이 방법을 사용의 예로, MFC 샘플에서 Testdll2.cpp을 참조 하십시오. [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)합니다.  
  
 MFC 이름이 지정 되는 MFC 개체의 동적 생성은 유사 합니다. MFC 개체의 deserialization 메커니즘의 일부 요구 된 `CRuntimeClass` 개체를 등록 하 여 동적으로 저장 된 순서에 따라 필요한 형식의 c + + 개체를 만들어 다시 구성할 수 있습니다.  
  
 MFC 샘플의 경우 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk), 같이 목록을 표시 합니다.  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
           MFCOxxD.DLL                |  
               |                      |  
           MFCDxxD.DLL                |  
               |                      |  
            MFCxxD.DLL            MFCxx.DLL  
```  
  
 여기서 *xx* 는 버전 번호입니다; 예를 들어 42 버전 4.2를 나타냅니다.  
  
 MFCxx.dll은 대개 마지막 리소스 및 클래스 목록에 있습니다. MFCxx.dll 모든 모든 표준 명령 Id에 대 한 프롬프트 문자열을 포함 하 여 표준 MFC 리소스를 포함 합니다. Dll과 클라이언트 응용 프로그램은 표준 MFC 리소스의 자체 복사본을 갖는 대신 MFCxx.dll의 공유 리소스에 의존 하는 목록의 끝에 배치 하는 것이 있습니다.  
  
 클라이언트 응용 프로그램의 네임 스페이스에는 리소스 및 모든 Dll의 클래스 이름을 병합 한다는 단점이 사용자 Id 또는 이름을 선택 하면에 주의 해야 합니다.  
  
 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) 샘플에서는 여러 헤더 파일을 사용 하 여 공유 리소스 네임 스페이스를 관리 합니다.  
  
 새 클래스를 파생 시켜 MFC 확장 DLL을 각 응용 프로그램에 대 한 추가 데이터를 유지 관리 하는 경우 **CDynLinkLibrary** 에서 만들어 및 `DllMain`합니다. DLL의 현재 응용 프로그램의 목록을 확인할 수를 실행할 때 **CDynLinkLibrary** 해당 특정 MFC 확장 DLL에 대 한 찾을 개체입니다.  
  
### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [MFC 확장 DLL 초기화](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [공유 리소스 파일 사용에 대 한 팁](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [기본 MFC Dll에 정적으로 MFC에 링크](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크 하는 기본 MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)