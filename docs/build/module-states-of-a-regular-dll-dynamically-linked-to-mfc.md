---
title: 일반 MFC DLL의 모듈 상태는 동적으로 MFC에 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15f533473ebe90d6d105ddeb57dcdcddd90e87b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369372"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>MFC에 동적으로 링크 하는 MFC 기본 DLL의 모듈 상태
MFC DLL에는 일반적인 MFC DLL에 동적으로 연결 하는 기능을 사용 하면 매우 복잡 한 일부 구성 합니다. 예를 들어 기본 MFC DLL과이 사용 하는 실행 파일이 둘 다 동적으로 연결할 수 및 MFC 확장 Dll MFC DLL에.  
  
 이 구성은 MFC 전역 데이터 포인터를 현재 같은 관련 문제가 발생 `CWinApp` 개체와 핸들 맵.  
  
 MFC 버전 4.0 하기 전에이 글로벌 데이터 내 MFC DLL에 상주 하 고 프로세스에서 모든 모듈에서 공유 되었습니다. Win32 DLL을 사용 하 여 각 프로세스는 DLL의 데이터의 자체 복사본을 가져오는 경우 때문에이 구성표는 쉽게 프로세스별 데이터를 추적 하는 방법을 제공 합니다. 또한 AFXDLL 모델 있을 것 하나만 것으로 가정 `CWinApp` 개체 및 하나의 핸들 프로세스의 맵, MFC DLL에서 이러한 항목을 추적할 수 없습니다.  
  
 그러나 MFC DLL에는 기본 MFC DLL에 동적으로 연결 하는 기능을 이제 둘 이상 있을 수 `CWinApp` 프로세스에서 개체-핸들 맵 중 두 개 이상의 설정도 있습니다. 어떻게 않는 MFC 추적을 계속 사용 해야 하는 기능과?  
  
 각 모듈 (응용 프로그램 또는 일반 MFC DLL)는 자체 복사본을이 전역 상태 정보를 제공 하는 솔루션은입니다. 에 대 한 호출 따라서 **AfxGetApp** 일반적인 MFC DLL에 대 한 포인터를 반환 합니다.는 `CWinApp` 실행 파일 슬라이드가 아니라 DLL에는 개체입니다. 이 모듈 당 복사본 MFC 글로벌 데이터의 모듈 상태 라고 하 고에 설명 되어 [MFC 기술 참고 58](../mfc/tn058-mfc-module-state-implementation.md)합니다.  
  
 MFC 공용 창 프로시저는 자동으로 올바른 모듈 상태로 전환 하므로 사용자가 기본 MFC DLL에 구현 된 모든 메시지 처리기에서 걱정할 필요가 없습니다. 그러나를 명시적으로 DLL에 대 한 책갈피로 현재 모듈 상태를 설정 해야 실행 파일의 기본 MFC DLL를 호출 합니다. 이 위해 사용 하 여는 **AFX_MANAGE_STATE** DLL에서 내보낸 모든 함수에는 매크로입니다. 이 작업은 DLL에서 내보낸 함수의 시작 부분에 다음 코드 줄을 추가 하 여 수행 됩니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [동적으로 MFC에 링크 하는 기본 MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 확장명 DLL](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)