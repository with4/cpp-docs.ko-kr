---
title: 일반 MFC Dll 동적으로 MFC에 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e20a3937786d65945256eeadcf0bf08b0314470
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>일반 MFC Dll이 MFC에 동적 연결
MFC DLL 동적으로 MFC에 링크 되는 일반적인 MFC를 내부적으로 사용 하는 DLL 이며 MFC 또는 비 MFC 실행 파일에서 DLL의 내보낸된 함수를 호출할 수 있습니다. 이름에서 알 수 있듯이 이러한 종류의 DLL은 MFC (MFC 공유 버전 라고도 함)의 동적 연결 라이브러리 버전을 사용 하 여 만들어집니다. 함수는 일반적으로 표준 C 인터페이스를 사용 하 여 MFC DLL 일반에서 내보내집니다.  
  
 추가 해야 합니다는 `AFX_MANAGE_STATE` 동적으로 MFC에 링크 하는 DLL에 대 한 책갈피로 현재 모듈 상태를 설정 하는 기본 MFC Dll에서 내보낸 모든 함수 시작 부분에는 매크로입니다. 이 작업은 DLL에서 내보낸 함수의 시작 부분에 다음 코드 줄을 추가 하 여 수행 됩니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 동적으로 MFC에 링크 하는 일반적인 MFC DLL에는 다음과 같은 기능이 있습니다.  
  
-   Visual c + + 4.0에서 도입 된 DLL의 새 형식입니다.  
  
-   클라이언트 실행 파일은 Dll (C, c + +, Pascal, Visual Basic 및 등);의 사용을 지 원하는 모든 언어로 작성할 수 있습니다. MFC 응용 프로그램 이어야 하지 않아도 됩니다.  
  
-   정적으로 연결 된 기본 MFC DLL와 달리 이러한 종류의 DLL MFC DLL (라고도 공유 MFC DLL)에 동적으로 연결 됩니다.  
  
-   이러한 종류의 DLL에 연결 된 MFC 가져오기 라이브러리는 MFC 확장 Dll 또는 MFC DLL을 사용 하 여 응용 프로그램에 사용 되는 것과 동일한:.lib MFCxx (D).  
  
 동적으로 MFC에 링크 하는 일반적인 MFC DLL에는 다음 요구 사항이 있습니다.  
  
-   이러한 Dll은으로 컴파일된 **_AFXDLL** MFC DLL에 연결 된 실행 파일 동일 하 게 정의 합니다. 하지만 **에서는 _USRDLL** 정적으로 MFC에 링크 하는 MFC 기본 DLL에서와 마찬가지로 정의 됩니다.  
  
-   이러한 종류의 DLL 인스턴스화해야는 `CWinApp`-클래스를 파생 합니다.  
  
-   이러한 종류의 DLL 사용의 `DllMain` MFC에서 제공 합니다. 모든 DLL 전용 초기화 코드를 추가 하는 `InitInstance` 멤버 함수, 종료 코드는 `ExitInstance` 일반적인 MFC 응용 프로그램에서와 같이 합니다.  
  
 이러한 종류의 DLL은 MFC의 동적 연결 라이브러리 버전을 사용 하므로 DLL에 대 한 책갈피로 현재 모듈 상태를 명시적으로 설정 해야 합니다. 이 위해 사용 하 여는 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) DLL에서 내보낸 모든 함수의 시작 부분에는 매크로입니다.  
  
 일반 MFC Dll 있어야는 `CWinApp`-파생 된 클래스 및 해당 응용 프로그램 클래스의 단일 개체는 MFC 응용 프로그램과 마찬가지로 합니다. 그러나는 `CWinApp` DLL의 개체에는 기본 메시지 펌프 마찬가지로 없는 `CWinApp` 응용 프로그램의 개체입니다.  
  
 `CWinApp::Run` 메커니즘 응용 프로그램 기본 메시지 펌프를 소유 하 고 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프를 호출 하는 DLL 내보낸 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자를 표시은 별도의 주 프레임 창, `CWinApp::PreTranslateMessage`합니다.  
  
 모든 DLL과 관련 된 초기화 배치는 `CWinApp::InitInstance` 일반적인 MFC 응용 프로그램에서와 같이 멤버 함수입니다. `CWinApp::ExitInstance` 의 멤버 함수 프로그램 `CWinApp` 파생된 클래스에서 제공 된 MFC 호출 `DllMain` DLL 로드 되기 전에 함수입니다.  
  
 공유 Dll MFCx0.dll 및 Msvcr*0.dll (또는 유사한 파일) 응용 프로그램과 함께 배포 해야 합니다.  
  
 동적으로 MFC에 링크 된 DLL MFC에 정적으로 연결할 수 없습니다. 기본 MFC Dll에 응용 프로그램 링크 동적으로 MFC에 링크 된 해당 다른 DLL과 마찬가지로 합니다.  
  
 기호는 일반적으로 표준 C 인터페이스를 사용 하 여 MFC DLL 일반에서 내보내집니다. MFC 기본 DLL에서 내보낸 함수 선언은 다음과 같습니다.  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 일반 MFC DLL 내에서 모든 메모리 할당 DLL; 내에 존재 합니다. DLL에 전달 하거나 호출 실행에서 다음 중 하나를 수신 하면 안:  
  
-   MFC 개체에 대 한 포인터  
  
-   MFC에서 할당 된 메모리에 대 한 포인터  
  
 위의 중 하나를 수행 해야 하거나 호출 실행 파일과 DLL 사이의 MFC 파생 개체를 전달 하는 경우에 MFC 확장 DLL을 빌드해야 합니다.  
  
 로 전달 하 포인터 할당 된 메모리에 C 런타임 라이브러리는 응용 프로그램과 DLL 사이의 데이터의 복사본을 만드는 경우에 안전 합니다. 삭제 하거나 이러한 포인터의 크기를 조정 하거나 않아야 메모리의 복사본을 만들지 않고이 사용 합니다.  
  
 매크로 사용 해야 하는 기본 MFC DLL에 세울 동적으로 MFC에 링크 때 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) 올바르게 MFC 모듈 상태를 전환 합니다. 이 작업은 DLL에서 내보낸 함수의 시작 부분에 다음 코드 줄을 추가 하 여 수행 됩니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 **AFX_MANAGE_STATE** MFC 확장 Dll 또는 정적으로 MFC에 링크 되는 기본 MFC Dll에 매크로 사용할 수 해야 합니다. 자세한 내용은 참조 [MFC 모듈 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)합니다.  
  
 작성, 빌드 및 MFC 기본 DLL을 사용 하는 방법의 예를 들어 샘플을 참조 하십시오. [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)합니다. MFC에 동적으로 연결 되는 기본 MFC Dll에 대 한 자세한 내용은 샘플에 대 한 요약의 "변환 DLLScreenCap를 동적으로 링크와 MFC DLL" 섹션을 참조 합니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [일반 MFC Dll 초기화](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [MFC에 동적으로 링크 하는 MFC 기본 DLL의 모듈 상태](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL의 종류](../build/kinds-of-dlls.md)