---
title: 일반 MFC Dll을 정적으로 MFC에 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48fdfb0b10541c1643ec49038e29cfa60c633d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383750"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>일반 MFC Dll을 정적으로 MFC에 링크
MFC DLL 정적으로 MFC에 링크 되는 일반적인 MFC를 내부적으로 사용 하는 DLL 이며 MFC 또는 비 MFC 실행 파일에서 DLL의 내보낸된 함수를 호출할 수 있습니다. 이름에서 알 수 있듯이 이러한 종류의 DLL의 MFC 정적 연결 라이브러리 버전을 사용 하 여 만들어집니다. 함수는 일반적으로 표준 C 인터페이스를 사용 하 여 MFC DLL 일반에서 내보내집니다. 작성, 빌드 및 MFC 기본 DLL을 사용 하는 방법의 예를 들어 샘플을 참조 하십시오. [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)합니다.  
  
 용어 USRDLL Visual c + + 설명서에 더 이상 사용 되는 참고 합니다. 정적으로 MFC에 링크 하는 MFC 기본 DLL은 이전 USRDLL와 동일한 특성입니다.  
  
 MFC에 정적으로 링크는 기본 MFC DLL에는 다음과 같은 기능이 있습니다.  
  
-   클라이언트 실행 파일은 Dll (C, c + +, Pascal, Visual Basic 및 등);의 사용을 지 원하는 모든 언어로 작성할 수 있습니다. MFC 응용 프로그램 이어야 하지 않아도 됩니다.  
  
-   DLL은 응용 프로그램에서 사용 하는 같은 MFC 정적 연결 라이브러리에 링크 합니다. 별도 Dll에 대 한 정적 연결 라이브러리의 버전은 더 이상.  
  
-   MFC의 4.0 버전 이전 USRDLLs 동일한 유형의 기본 MFC Dll에 정적으로 MFC에 링크와 기능을 제공 합니다. Visual c + + 버전 4.0을 USRDLL 라는 용어는 사용 되지 않습니다.  
  
 MFC에 정적으로 연결 하는 기본 MFC DLL에는 다음 요구 사항을 있습니다.  
  
-   이러한 종류의 DLL에서 파생 된 클래스를 인스턴스화해야 `CWinApp`합니다.  
  
-   이러한 종류의 DLL 사용의 `DllMain` MFC에서 제공 합니다. 모든 DLL 전용 초기화 코드를 추가 하는 `InitInstance` 멤버 함수, 종료 코드는 `ExitInstance` 일반적인 MFC 응용 프로그램에서와 같이 합니다.  
  
-   용어 USRDLL는 사용 되지 않는, 경우에 정의 해야 "**에서는 _USRDLL**" 컴파일러 명령줄에서. 이 정의 선언을 MFC 헤더 파일에서 가져올 결정 합니다.  
  
 일반 MFC Dll 있어야는 `CWinApp`-파생 된 클래스 및 해당 응용 프로그램 클래스의 단일 개체는 MFC 응용 프로그램과 마찬가지로 합니다. 그러나는 `CWinApp` DLL의 개체에는 기본 메시지 펌프 마찬가지로 없는 `CWinApp` 응용 프로그램의 개체입니다.  
  
 `CWinApp::Run` 메커니즘 응용 프로그램 기본 메시지 펌프를 소유 하 고 DLL에 적용 되지 않습니다. 응용 프로그램의 기본 메시지 펌프 호출 하 여 해당 DLL에서 내보내기 루틴을 호출 해야 경우 DLL 모덜리스 대화 상자은 별도의 주 프레임 창는 `CWinApp::PreTranslateMessage` DLL의 응용 프로그램 개체의 멤버 함수입니다.  
  
 이 함수의 예를 들어 DLLScreenCap 샘플을 참조 하세요.  
  
 기호는 일반적으로 표준 C 인터페이스를 사용 하 여 MFC DLL 일반에서 내보내집니다. 일반 MFC DLL에서 내보낸 함수 선언은 모양은 다음과 같습니다.  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 일반 MFC DLL 내에서 모든 메모리 할당 DLL; 내에 존재 합니다. DLL에 전달 하거나 호출 실행에서 다음 중 하나를 수신 하면 안:  
  
-   MFC 개체에 대 한 포인터  
  
-   MFC에서 할당 된 메모리에 대 한 포인터  
  
 위의 항목 중 하나를 수행 하거나 호출 실행 파일과 DLL 사이의 MFC 파생 개체를 전달 해야 할 경우에 MFC 확장 DLL 빌드해야 합니다.  
  
 로 전달 하 포인터 할당 된 메모리에 C 런타임 라이브러리는 응용 프로그램과 DLL 사이의 데이터의 복사본을 만드는 경우에 안전 합니다. 삭제 하거나 이러한 포인터의 크기를 조정 하거나 않아야 메모리의 복사본을 만들지 않고이 사용 합니다.  
  
 정적으로 MFC에 링크 된 DLL 공유 MFC Dll에 동적으로 연결할 수 없습니다. 다른 DLL;와 마찬가지로 응용 프로그램에 동적으로 바인딩되어 정적으로 MFC에 링크 된 DLL 다른 DLL과 마찬가지로 응용 프로그램에 연결 합니다.  
  
 표준 MFC 정적 연결 라이브러리에 설명 된 규칙에 따라 이름을 [MFC Dll에 대 한 명명 규칙](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)합니다. 그러나 MFC 버전 3.0 이상 이므로 더 이상에 연결 된 원하는 MFC 라이브러리의 버전을 링커로 수동으로 지정 하는 데 필요한. 대신, MFC 헤더 파일을 자동으로 확인와 같은 올바른 버전에 따라 전처리기에서 링크할 MFC 라이브러리의 정의  **\_디버그** 또는 **_UNICODE**합니다. MFC 헤더 파일 특정 버전의 MFC 라이브러리에 연결 하 여 링커가 /DEFAULTLIB 지시문을 추가 합니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [일반 MFC Dll 초기화](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC DLL 만들기](../mfc/reference/mfc-dll-wizard.md)  
  
-   [동적으로 MFC에 링크된 기본 MFC DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 확장명 DLL](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL의 종류](../build/kinds-of-dlls.md)