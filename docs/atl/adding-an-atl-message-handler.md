---
title: "ATL 메시지 처리기 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4358dc54589971c559bec48adf77252d4f4cda28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-message-handler"></a>ATL 메시지 처리기 추가
메시지 처리기 (Windows 메시지를 처리 하는 멤버 함수)에 컨트롤을 추가 하려면 먼저 클래스 뷰에서 컨트롤을 선택 합니다. 다음 엽니다는 **속성** 창에서는 **메시지** 아이콘을 클릭 하 여 드롭다운 목록 옆에 필요한 메시지 상자에서 제어 합니다. 이렇게 하면 컨트롤의 헤더 파일 및 컨트롤의.cpp 파일에서 처리기의 기본 구현에서 메시지 처리기에 대 한 선언을 추가 됩니다. 또한 메시지 맵을 추가할 되며 처리기에 대 한 항목을 추가 합니다.  
  
 ATL에서 메시지 처리기를 추가 하는 것에 메시지 처리기는 MFC 클래스를 추가 하는 것과 비슷합니다. 참조 [MFC 메시지 처리기 추가](../mfc/reference/adding-an-mfc-message-handler.md) 자세한 정보에 대 한 합니다.  
  
 다음 조건이 ATL 메시지 처리기 추가에 적용 됩니다.  
  
-   메시지 처리기 MFC와 같은 명명 규칙을 따릅니다.  
  
-   새 메시지 맵 항목은 기본 메시지 지도에 추가 됩니다. 마법사는 대체 메시지 맵 및 체인를 인식 하지 못합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)

