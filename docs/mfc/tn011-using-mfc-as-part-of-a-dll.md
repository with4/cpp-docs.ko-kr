---
title: 'TN011: DLL의 일부로 MFC 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dll
dev_langs:
- C++
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b558bb373416338f4136a6142ca6d491b28b510
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951460"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: DLL의 일부로 MFC 사용
이 노트 Windows 동적 연결 라이브러리 (DLL)의 일부로 MFC 라이브러리를 사용할 수 있도록 기본 MFC Dll에 설명 합니다. Windows Dll 및 이들을 빌드하는 방법에 잘 알고 한다고 가정 합니다. MFC 확장 Dll에 대 한 정보를 만들 수 있는와 MFC 라이브러리에 대 한 확장 참조 [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)합니다.  
  
## <a name="dll-interfaces"></a>DLL 인터페이스  
 일반 MFC Dll 인터페이스는 응용 프로그램과 DLL 사이의 C와 같은 함수 또는 명시적으로 내보낸된 클래스에 지정 된 가정 합니다. MFC 클래스 인터페이스를 내보낼 수 없습니다.  
  
 MFC를 사용 하는 DLL과 응용 프로그램 모두 원하는 경우 MFC 라이브러리의 공유 버전을 사용 하거나 또는 라이브러리의 복사본에 정적으로 링크를 선택 하는 둘 다입니다. 응용 프로그램 및 DLL 둘 다 사용할 수 MFC 라이브러리의 표준 버전 중 하나입니다.  
  
 일반 MFC Dll 몇 가지 이점이 있습니다.  
  
-   DLL을 사용 하는 응용 프로그램 MFC를 사용 하지 않아도 및 Visual c + + 응용 프로그램을 사용할 필요가 없습니다.  
  
-   MFC에 정적으로 링크 하는 기본 MFC Dll에 있는 DLL의 크기는 사용 및 연결 하는 MFC 및 C 런타임 루틴에만 다릅니다.  
  
-   MFC에 동적으로 연결 하는 기본 MFC Dll에 있는 공유 버전의 MFC 사용 하 여 메모리에 공간 절약에 대해서는 중요할 수 있습니다. 하지만 Mfc 공유 Dll을 배포 해야*\<버전 >*.dll 및 Msvvcrt*\<버전 >*.dll DLL로 합니다.  
  
-   DLL 디자인은 독립적 클래스를 구현 하는 방법입니다. DLL 디자인 원하는 Api만 내보냅니다. 결과적으로, 구현 변경 되 면 일반 MFC Dll은 계속 유효 합니다.  
  
-   일반 MFC dll에 정적으로 MFC에 링크 하는 다른 버전의 MFC DLL 보다 하거나 그 반대로 응용 프로그램에 문제가 없는지 없는 DLL과 응용 프로그램 MFC를 사용 합니다. 없기 때문에 각 DLL 또는 EXE에 MFC 라이브러리는 정적으로 연결 되어 있는 버전에 대 한 질문이 되지 않았습니다.  
  
## <a name="api-limitations"></a>API 제한 사항  
 MFC 기능 일부 기술적 제한 사항을 인해 DLL 버전에 적용 되지 않습니다 없거나 해당 서비스 응용 프로그램에서 일반적으로 제공 됩니다. 적용할 수 있는 유일한 함수는 현재 버전의 MFC `CWinApp::SetDialogBkColor`합니다.  
  
## <a name="building-your-dll"></a>DLL 작성  
 MFC 기호에 정적으로 링크 하는 기본 MFC Dll에 컴파일할 때 `_USRDLL` 및 `_WINDLL` 정의 되어야 합니다. DLL 코드에 다음 컴파일러 스위치도 컴파일해야 합니다.  
  
- **/ D_WINDLL** DLL에 대 한 컴파일을 나타냅니다  
  
- **/ D_USRDLL** 기본 MFC DLL을 작성 하는 지정  
  
 또한 이러한 기호를 정의 하 고 동적으로 MFC에 링크 되는 기본 MFC Dll을 컴파일할 때 이러한 컴파일러 스위치를 사용 해야 합니다. 기호 또한 `_AFXDLL` 정의 해야 하 고 DLL 코드를 컴파일해야 합니다.:  
  
- **/ D_AFXDLL** 작성할 수 있도록 동적으로 MFC에 링크 하는 MFC 기본 DLL 지정  
  
 응용 프로그램과 DLL 사이의 (Api) 인터페이스를 명시적으로 내보내야 합니다. 낮은 대역폭 되도록 인터페이스를 정의할 수 있는 경우 C 인터페이스만 사용 하는 것이 좋습니다. 직접 C 인터페이스는 더 복잡 한 c + + 클래스 보다 유지 관리가 더 용이 합니다.  
  
 C 및 c + + 파일에 의해 포함 될 수 있는 별도 헤더에 Api를 배치 합니다. MFC 고급 개념 샘플에서 ScreenCap.h 헤더 참조 [DLLScreenCap](../visual-cpp-samples.md) 예에 대 한 합니다. 함수를 내보내려면 입력이 `EXPORTS` 모듈 정의 파일의 섹션 (합니다. DEF) 하거나 포함 `__declspec(dllexport)` 함수 정의에 있습니다. 사용 하 여 `__declspec(dllimport)` 클라이언트 실행 파일은으로 이러한 함수를 가져올 수 있습니다.  
  
 동적으로 MFC에 링크 되는 기본 MFC Dll에서 내보낸 모든 함수 시작 부분에 AFX_MANAGE_STATE 매크로 추가 해야 합니다. 이 매크로 DLL에 대 한을 현재 모듈 상태를 설정합니다. 이 매크로 사용 하려면 DLL에서 내보낸 함수의 시작 부분에 다음 코드 줄을 추가 합니다.  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## <a name="winmain---dllmain"></a>WinMain DllMain->  
 MFC 라이브러리는 표준 Win32 정의 `DllMain` 진입점을 초기화 하는 프로그램 [CWinApp](../mfc/reference/cwinapp-class.md) 일반적인 MFC 응용 프로그램에서와 같이 개체를 파생 합니다. 모든 DLL과 관련 된 초기화 배치는 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 일반적인 MFC 응용 프로그램에서와 같이 메서드.  
  
 [cwinapp:: Run](../mfc/reference/cwinapp-class.md#run) 메커니즘 응용 프로그램 기본 메시지 펌프를 소유 하 고 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프를 호출 하는 DLL 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자를 표시 합니다.은 별도의 주 프레임 창, [경우](../mfc/reference/cwinapp-class.md#pretranslatemessage)합니다.  
  
 이 함수는 사용 하기 위해 DLLScreenCap 예제를 참조 하십시오.  
  
 `DllMain` MFC는 호출에서 제공 하는 함수는 [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) 에서 파생 된 클래스의 메서드로 `CWinApp` DLL 언로드되기 전에 합니다.  
  
## <a name="linking-your-dll"></a>DLL에 링크  
 MFC에 정적으로 링크 하는 일반 MFC Dll과 DLL Nafxcwd.lib 또는 Nafxcw.lib 및 Libcmt.lib 라는 C 런타임 버전을 연결 해야 합니다. 이러한 라이브러리는 미리 작성 된 및 Visual c + + 프로그램을 실행할 때 지정 하 여 설치할 수 있습니다.  
  
## <a name="sample-code"></a>샘플 코드  
 전체 샘플 DLLScreenCap 프로그래밍 MFC 고급 개념 샘플을 참조 하십시오. 이 샘플에서 주목할 몇 가지 흥미로운 작업은 다음과 같습니다.  
  
-   DLL의 컴파일러 플래그 및 응용 프로그램의 서로 다릅니다.  
  
-   연결 선 및 합니다. 응용 프로그램에 대 한 DLL에 대 한 DEF 파일 권한과 다릅니다.  
  
-   응용 프로그램 DLL을 사용 하는 c + +의 필요가 없습니다.  
  
-   인터페이스는 응용 프로그램과 DLL 사이의 DLLScreenCap.def와 API C 또는 c + +에서 사용 되 고 내보내집니다.  
  
 다음 예제에서는 일반적인 정적으로 MFC에 링크 MFC DLL에 정의 된 API를 보여 줍니다. 이 예제에서는 선언에 포함 되어는 `extern "C" { }` c + + 사용자에 대 한 블록입니다. 이 여러 가지 이점이 있습니다. 첫째, 사용자 DLL Api을 비 c + + 클라이언트 응용 프로그램에서 사용할 수 있도록 만듭니다. 둘째, c + + 이름 손상 수에 적용 되지 것입니다 내보낸된 이름 때문에 DLL 오버 헤드가 줄어듭니다. 마지막으로 보다 쉽게에 명시적으로 추가 하는 합니다. 이름 손상에 대해 걱정할 필요 없이 DEF (에 대 한 서 수로 내보내기) 파일입니다.  
  
```  
#ifdef __cplusplus  
extern "C" {  
#endif  /* __cplusplus */  
 
struct TracerData  
{  
    BOOL bEnabled;  
    UINT flags;  
};  
 
BOOL PromptTraceFlags(TracerData FAR* lpData);

 
#ifdef __cplusplus  
}  
#endif  
```  
  
 API에서 사용 되는 구조는 MFC 클래스에서 파생 되지 않은 되며 API 헤더에 정의 됩니다. 이렇게 하면 DLL과 응용 프로그램 사이의 인터페이스의 복잡성 줄어들고 C 프로그램에서 DLL을 사용할 수 있도록 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

