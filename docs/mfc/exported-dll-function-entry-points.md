---
title: 내보낸 DLL 함수 시작 지점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1be4c74a48f1367369582b433a2a833ceb8e1976
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343855"
---
# <a name="exported-dll-function-entry-points"></a>내보낸 DLL 함수 시작 지점
DLL의 내보낸된 함수에 대 한 사용는 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) DLL 모듈에서 호출 응용 프로그램의 DLL로 전환 하는 경우 적절 한 글로벌 상태를 유지 하는 매크로입니다.  
  
 이 매크로 설정 하는 호출 되 면 `pModuleState`에 대 한 포인터는 `AFX_MODULE_STATE` 포함 하는 함수 범위의 나머지 부분에 대 한 유효한 모듈 상태와 모듈에 대 한 글로벌 데이터를 포함 하는 구조입니다. 매크로 포함 하는 범위를 벗어나면 자동으로 이전 유효한 모듈 상태 복원 됩니다.  
  
 인스턴스를 구성 하 여 수행 됩니다이 전환는 **AFX_MODULE_STATE** 스택에 클래스입니다. 생성자에서이 클래스를 받고 현재 모듈 상태에 대 한 포인터 및 멤버 변수에 저장를 설정 하는 다음 `pModuleState` 새 유효한 모듈 상태입니다. 이 클래스는 해당 소멸자에서 유효한 모듈 상태와 해당 멤버 변수에 저장 된 포인터를 복원 합니다.  
  
 내보낸된 함수, 사용자 DLL에 대화 상자를 시작 하는 것과 같은 있는 경우 함수의 시작 부분에 다음 코드를 추가 해야 합니다.  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.  
  
 경우 리소스 Dll에서 문제가 발생 합니다는 `AFX_MANAGE_STATE` 매크로 사용 되지 않습니다. 기본적으로 MFC 리소스 템플릿을 로드 하는 주 응용 프로그램의 리소스 핸들을 사용 합니다. 이 서식 파일은 실제로 DLL에 저장 됩니다. 근본 원인이 MFC의 모듈 상태 정보도 전환 하지는 `AFX_MANAGE_STATE` 매크로입니다. 리소스 핸들 MFC 모듈 상태에서 복구 됩니다. 모듈 상태를 전환 하지 않으면 잘못 리소스 핸들을 사용 하면 됩니다.  
  
 `AFX_MANAGE_STATE` 모든 DLL의에서 함수에 필요 하지 않습니다. 예를 들어 `InitInstance` 없이 응용 프로그램에는 MFC 코드에서 호출할 수 있습니다 `AFX_MANAGE_STATE` MFC 모듈 상태 하기 전에 자동으로 이동 하기 때문에 `InitInstance` 및 후에 백업 하는 스위치 다음 `InitInstance` 반환 합니다. 모든 메시지 맵 처리기에도 마찬가지입니다. 일반 MFC Dll에는 실제로 메시지를 라우팅하기 전에 모듈 상태를 자동으로 전환 하는 특수 한 마스터 창 프로시저 있는데  
  
## <a name="see-also"></a>참고 항목  
 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)

