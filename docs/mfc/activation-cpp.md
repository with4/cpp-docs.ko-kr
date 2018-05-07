---
title: 활성화 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b6d6e9313092a8f9a0a11967c7c6a62ed15e15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="activation-c"></a>활성화(C++)
이 문서에서는 OLE 항목의 비주얼 편집 활성화의 역할을 설명 합니다. OLE 항목이 컨테이너 문서에 포함 된, 사용할 필요할 수 있습니다. 이 수행 하려면 사용자가 해당 항목을 활성화 하는 항목을 두 번 클릭 합니다. 정품 인증에 대 한 가장 자주 나타나는 활동 편집 중입니다. 많은 현재 OLE 항목 편집을 위해 활성화 될 때 메뉴 및 도구 모음 항목을 만든 서버 응용 프로그램에 속한 반영 하도록 변경 하려면 현재 프레임 창에 발생 합니다. 이 동작을 같이 내부 활성화를 알려진 컨테이너 문서 창 종료 하지 않고 복합 문서에 포함 된 모든 항목을 편집할 수 있습니다.  
  
 별도 창에 포함 된 OLE 항목을 편집할 수 이기도 합니다. 컨테이너 또는 서버 응용 프로그램에는 내부 활성화를 지원 하지 않는 경우 발생 합니다. 이 경우 사용자가 포함된 된 항목을 별도 창에서 서버 응용 프로그램이 시작 되 고 포함된 된 항목 자체 문서로 나타납니다. 사용자가이 창에서 항목을 편집 합니다. 편집이 완료 되 면 사용자는 서버 응용 프로그램을 닫는 하 고 컨테이너 응용 프로그램에 반환 합니다.  
  
 대신 사용자가 선택할 수 "편집 열고"와  **\<개체 > 열고** 명령을 **편집** 메뉴. 개체는 별도 창에서 열립니다.  
  
> [!NOTE]
>  별도 창에 포함 된 항목을 편집 OLE 버전 1에서에서 표준 동작와 일부 OLE 응용 프로그램의 편집이 스타일에만 지원 될 수 있습니다.  
  
 내부 활성화 문서 만들기에 대 한 문서 중심적인 액세스를 수준을 올립니다. 사용자 작업을 응용 프로그램 간에 전환 하지 않고 복합 문서를 단일 엔터티로 처리할 수 있습니다. 그러나 내부 활성화 연결 항목의 포함 된 항목에 대해서만 사용 됩니다: 별도 창에서 편집 해야 합니다. 즉, 연결된 된 항목이 실제로 서로 다른 위치에 저장 됩니다. 연결된 된 항목을 편집 하는 이루어집니다 실제 데이터 즉, 컨텍스트 내에서 데이터가 저장 됩니다. 별도 창에 연결된 된 항목을 편집 데이터 다른 문서에 속하는 사용자를 게 알립니다.  
  
 MFC는 중첩 된 위치에서 활성화를 지원 하지 않습니다. 컨테이너/서버 응용 프로그램을 작성 하는 경우 그리고 다른 컨테이너 내부 활성화에 포함 된 컨테이너/서버 것 수 없는 내부 내부에 포함 된 개체를 활성화 합니다.  
  
 사용자가 포함된 된 항목에 어떻게 되나요 항목에 대해 정의 된 동사에 따라 달라 집니다. 자세한 내용은 참조 [활성화: 동사](../mfc/activation-verbs.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE](../mfc/ole-in-mfc.md)   
 [컨테이너](../mfc/containers.md)   
 [서버](../mfc/servers.md)

