---
title: "방법: 메시지 맵 상호 참조를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords: windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25f78fb2e2c5700cbb1f7c8dcb093795ce001c13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-the-message-map-cross-reference"></a>방법: 메시지 맵 상호 참조 사용
레이블이 지정 된 항목에 \<memberFxn >, 파생에 대 한 직접 멤버 함수를 작성 [CWnd](../../mfc/reference/cwnd-class.md) 클래스입니다. 함수 이름은 원하는 대로 지정 합니다. 와 같은 다른 함수 `OnActivate`, 클래스의 멤버 함수는 `CWnd`합니다. 에 메시지를 전달 하 고 호출 하는 경우는 `DefWindowProc` Windows 함수입니다. Windows 알림 메시지를 처리 하려면 해당 재정의 `CWnd` 파생된 클래스에는 함수입니다. 함수는 기본 클래스를 사용 하려면 기본 클래스에서 재정의 된 함수를 호출 해야 하 고 Windows 메시지에 응답 합니다.  
  
 모든 경우에는 함수 프로토타입에 배치 된 `CWnd`-파생된 클래스 헤더 및 메시지 맵 항목 표시 된 것 처럼 코드.  
  
 다음과 같은 용어가 사용 됩니다.  
  
|용어|정의|  
|----------|----------------|  
|ID|모든 사용자 지정 메뉴 항목 ID (**WM_COMMAND** 메시지) 또는 ID (자식 창 알림 메시지)를 제어 합니다.|  
|"message"와 "wNotifyCode"|WINDOWS에 정의 된 대로 windows Id를 메시지입니다. 8.|  
|nMessageVariable|반환 값이 포함 된 변수의 이름을 **RegisterWindowMessage** Windows 함수입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)

