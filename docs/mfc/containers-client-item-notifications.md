---
title: "컨테이너: 클라이언트 항목 알림 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58f995893f580ef41c27653a30e94d1f106fceb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-item-notifications"></a>컨테이너: 클라이언트 항목 알림
이 문서에서는 MFC 프레임 워크 클라이언트 응용 프로그램의 문서에 항목을 수정 하는 서버 응용 프로그램을 호출 하는 재정의 가능한 함수를 설명 합니다.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) 서버 응용 프로그램이 라고도 하는 구성 요소 응용 프로그램의 요청에 대 한 응답에서에 호출 되는 몇 가지 재정의 가능한 함수를 정의 합니다. 이러한 함수는 일반적으로 알림으로 작동합니다. 컨테이너 응용 프로그램을의 위치에의 한 변경 내용을 편집, 항목 조작 때 사용자가 변경 또는 스크롤, 활성화 등의 다양 한 이벤트를 알려 줍니다.  
  
 프레임 워크에 대 한 호출을 통해 변경 내용의 컨테이너 응용 프로그램에 알립니다 `COleClientItem::OnChange`는 overridable 함수 구현이 필요 합니다. 이 보호 된 함수는 두 개의 인수를 받습니다. 첫 번째 서버 항목을 변경한 이유를 지정 합니다.  
  
|알림|의미|  
|------------------|-------------|  
|`OLE_CHANGED`|OLE 항목의 모양 변경 되었습니다.|  
|`OLE_SAVED`|OLE 항목이 저장 되었습니다.|  
|`OLE_CLOSED`|OLE 항목 종료 되었습니다.|  
|**OLE_RENAMED**|OLE 항목을 포함 하는 서버 문서 이름이 변경 되었습니다.|  
|`OLE_CHANGED_STATE`|OLE 항목은 다른 한 상태에서 변경 되었습니다.|  
|**OLE_CHANGED_ASPECT**|OLE 항목의 그리기 모양은 프레임 워크에 의해 변경 되었습니다.|  
  
 이러한 값은 고 **OLE_NOTIFICATION** AFXOLE에 정의 된 열거형입니다. 8.  
  
 이 함수에 두 번째 인수는 항목이 변경 된 방식을 또는 입력 한 상태를 지정 합니다.  
  
|첫 번째 인수는 경우|두 번째 인수|  
|----------------------------|---------------------|  
|`OLE_SAVED` 또는 `OLE_CLOSED`|사용 되지 않습니다.|  
|`OLE_CHANGED`|변경 된 OLE 항목의 모양을 지정 합니다.|  
|`OLE_CHANGED_STATE`|입력 되 고 상태를 설명 (`emptyState`, **loadedState**, `openState`, `activeState`, 또는 `activeUIState`).|  
  
 클라이언트 항목 간주 될 수 있는 상태에 대 한 자세한 내용은 참조 [컨테이너: 클라이언트 항목 상태](../mfc/containers-client-item-states.md)합니다.  
  
 프레임 워크를 호출 하 여 `COleClientItem::OnGetItemPosition` 때 항목이 활성화 되 고 내부 편집 합니다. 구현 내부 편집을 지 원하는 응용 프로그램에 대 한 필수입니다. MFC 응용 프로그램 마법사에 대 한 항목의 좌표를 할당 하는 기본 구현을 제공는 `CRect` 에 인수로 전달 되는 개체 `OnGetItemPosition`합니다.  
  
 OLE 항목의 위치 또는 크기 내부 편집 하는 동안 변경 되 면 항목의 위치와 클리핑 사각형에 대 한 컨테이너의 정보를 업데이트 해야 하며 서버에서 변경 내용에 대 한 정보를 받아야 합니다. 프레임 워크를 호출 하 여 `COleClientItem::OnChangeItemPosition` 이 목적을 위해 합니다. MFC 응용 프로그램 마법사는 기본 클래스의 함수를 호출 하는 재정의 제공 합니다. 응용 프로그램 마법사가 작성 하는 함수를 편집 해야 프로그램 `COleClientItem`-파생 클래스는 클라이언트 항목 개체에서 모든 정보를 업데이트 되도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨테이너](../mfc/containers.md)   
 [컨테이너: 클라이언트 항목 상태](../mfc/containers-client-item-states.md)   
 [COleClientItem::OnChangeItemPosition](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

