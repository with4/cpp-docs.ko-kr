---
title: 메시지 처리 및 명령 대상 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7184a6e8df67dfd220173c42bfa3e0580bd2cd3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349469"
---
# <a name="message-handling-and-command-targets"></a>메시지 처리 및 명령 대상
명령 디스패치 인터페이스 `IOleCommandTarget` 쿼리 명령을 실행 하는 간단 하 고 확장 가능한 메커니즘을 정의 합니다. 이 메커니즘은 자동화의 보다 간단 `IDispatch` ; 명령의 표준 집합에 전적으로 사용 하기 때문에 거의 명령에는 인수를 하며 형식 정보가 없는 관련 된 (형식 안전성도 명령 인수에 대 한 감소 됨).  
  
 자체로 식별 되는 "명령 그룹"에 속해 있어서 각 명령은 명령 디스패치 인터페이스 디자인에는 **GUID**합니다. 따라서 새 그룹을 정의 하 고 다른 공급 업체 또는 Microsoft와 조정 하기 위해 필요 없이 해당 그룹 내의 모든 명령을 정의할 수 누구나 합니다. (이 기본적으로 서의 정의 동일한 방법을 **dispinterface** 플러스 **Dispid** 자동화에서 합니다. 중첩이 됩니다 여기에서이 명령 라우팅 메커니즘 대규모로 스크립팅/프로그래밍 아닌와 명령 라우팅에 자동화 핸들은 있지만.)  
  
 `IOleCommandTarget` 다음과 같은 시나리오를 처리합니다.  
  
-   개체를 개체의 도구 모음은 일반적으로 표시 하 고 같은 컨테이너 명령 중 일부에 대 한 개체의 도구 모음 단추가 되어 활성화 될 때 **인쇄**, **인쇄 미리 보기**,  **저장**, `New`, **확대/축소**, 등입니다. (개체를 제거 하는 표준 권장 되는 내부 활성화에서 또는 도구 모음에서 이러한 단추 적어도 비활성화 합니다. 이 디자인에서는 해당 명령을 활성화 하 고 적절 한 처리기를 아직 라우팅할 수 있습니다.) 현재 컨테이너에 이러한 명령을 디스패치 개체에 대 한 장치가 있습니다.  
  
-   액티브 문서가 액티브 문서 컨테이너 (예: Office Binder)에 포함 된 경우 컨테이너 보내야 할 수도 있습니다 명령을 이러한 **인쇄**, **페이지 설정**, **속성**, 및 다른 사용자가 포함 된 액티브 문서.  
  
 이 간단한 명령 라우팅 기존 자동화 표준을 통해 처리 될 수 및 `IDispatch`합니다. 그러나 오버 헤드는 데 관련 된 `IDispatch` 에 여기에서 필요한 것 보다 더 하므로 `IOleCommandTarget` 같은 달성 하기 위해 간단한 방법을 제공 합니다.  
  
```  
interface IOleCommandTarget : IUnknown  
    {  
    HRESULT QueryStatus(  
        [in] GUID *pguidCmdGroup,  
        [in] ULONG cCmds,  
        [in,out][size_is(cCmds)] OLECMD *prgCmds,  
        [in,out] OLECMDTEXT *pCmdText);  
    HRESULT Exec(  
        [in] GUID *pguidCmdGroup,  
        [in] DWORD nCmdID,  
        [in] DWORD nCmdExecOpt,  
        [in] VARIANTARG *pvaIn,  
        [in,out] VARIANTARG *pvaOut);  
    }  
```  
  
 `QueryStatus` 메서드 여기 명령 집합이 특정 집합으로 식별 되 고 있는지 테스트 하는 **GUID**, 지원 됩니다. 이 호출은 배열을 채웁니다 **OLECMD** 값 (구조) 지원 되는 목록이 명령으로 이름을 명령 및/또는 상태 정보를 설명 하는 텍스트를 반환 합니다. 명령을 호출 하려면 호출자에 게 때, 명령으로 전달할 수 (및 집합 **GUID**)를 **Exec** 옵션 및 인수 함께 돌아가기 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 문서 컨테이너](../mfc/active-document-containers.md)

