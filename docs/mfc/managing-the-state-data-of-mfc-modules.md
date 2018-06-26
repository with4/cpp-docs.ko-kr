---
title: MFC 모듈의 상태 데이터 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5c2bced4f7f04cf75c72e68db0f99e0f89d2566
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930518"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>MFC 모듈의 상태 데이터 관리
이 문서에서는 MFC 모듈 및 (path 코드는 응용 프로그램을 통해 실행할 때) 실행 흐름을 입력 하 고 하거나 모듈에서 벗어날 때이 상태가 업데이트 되는 방법을 상태 데이터를 설명 합니다. AFX_MANAGE_STATE 및 METHOD_PROLOGUE 매크로 함께 모듈 상태 전환에 대해서도 설명 합니다.  
  
> [!NOTE]
>  용어 "모듈" 여기 실행 프로그램 또는 DLL (또는 집합에 Dll의) 응용 프로그램의 나머지와 독립적으로 작동 하는, 참조 했지만 공유 MFC DLL의 복사본을 사용 합니다. ActiveX 컨트롤은 모듈의 일반적인 예입니다.  
  
 다음 그림에 나와 있는 것 처럼 MFC 응용 프로그램에서 사용 되는 각 모듈에 대 한 상태 데이터에 있습니다. 이 데이터의 예로 Windows 인스턴스 핸들 (리소스 로드에 사용), 현재 포인터 `CWinApp` 및 `CWinThread` 응용 프로그램, OLE 모듈 참조 수 및 다양 한 간의 연결을 유지 관리 하는 맵 개체 Windows 핸들 및 MFC 개체의 해당 인스턴스 개체입니다. 그러나 응용 프로그램에서 여러 모듈이 사용, 각 모듈의 상태 데이터 않습니다 응용 프로그램 너비입니다. 대신, 각 모듈에 MFC의 상태 데이터의 개인 자체 복사본이 있습니다.  
  
 ![단일 모듈의 데이터를 상태 &#40;응용 프로그램&#41;](../mfc/media/vc387n1.gif "vc387n1")  
단일 모듈(응용 프로그램)의 상태 데이터  
  
 모듈의 상태 데이터 구조에 포함 하 고는 항상 해당 구조에 대 한 포인터를 통해 사용할 수 있습니다. 다음 그림에 나와 있는 것 처럼 실행 흐름이 특정 모듈을 입력 하면 해당 모듈의 상태는 "현재" 또는 "효율적인" 상태 여야 합니다. 따라서 각 스레드 개체에 해당 응용 프로그램의 유효한 상태 구조체에 대 한 포인터입니다. 이 포인터 전혀 업데이트를 유지 시간이 응용 프로그램의 글로벌 상태를 관리 하 고 각 모듈의 상태의 무결성을 유지 하는 데 반드시 필요 합니다. 전역 상태가 잘못 된 관리 예기치 않은 응용 프로그램 동작이 발생할 수 있습니다.  
  
 ![여러 모듈의 데이터를 상태](../mfc/media/vc387n2.gif "vc387n2")  
여러 모듈의 상태 데이터  
  
 즉, 각 모듈은 올바르게 모든 진입점에 대 한 모듈 상태 간 전환 하는 일을 담당 합니다. "진입점" 실행 흐름을 모듈의 코드를 입력할 수 있는 곳 이면 어디서입니다. 진입점은 다음과 같습니다.  
  
-   [DLL에서 내보낸된 함수](../mfc/exported-dll-function-entry-points.md)  
  
-   [COM 인터페이스의 멤버 함수](../mfc/com-interface-entry-points.md)  
  
-   [창 프로시저](../mfc/window-procedure-entry-points.md)  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

