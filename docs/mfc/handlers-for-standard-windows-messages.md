---
title: "표준 Windows 메시지에 대 한 처리기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afx_msg
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91df3462297c2a45a8938d815cc3b6a3b8ca6edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-standard-windows-messages"></a>표준 Windows 메시지에 대한 처리기
표준 Windows 메시지에 대 한 처리기를 기본 (**WM_**) 클래스에는 미리 정의 `CWnd`합니다. 이 클래스 라이브러리는 메시지 이름을 기반으로 이러한 처리기의 이름을 지정합니다. 예를 들어 `WM_PAINT` 메시지에 대한 처리기는 다음과 같이 `CWnd`에 선언됩니다.  
  
 `afx_msg void OnPaint();`  
  
 **afx_msg** 키워드는 c + +의 효과 제안 **가상** 처리기 서로 구분 하 여 키워드 `CWnd` 멤버 함수입니다. 하지만 이러한 함수는 실제로 가상이 아니며, 대신 메시지 맵을 통해 구현됩니다. 메시지 맵은 C++ 언어의 확장이 아닌 표준 전처리기 매크로에만 의존합니다. **afx_msg** 키워드 전처리 후 공백으로 확인 합니다.  
  
 기본 클래스에 정의된 처리기를 재정의하려면 단순히 파생된 클래스의 동일 프로토타입으로 함수를 정의하고 처리기에 대한 메시지-맵 항목을 만듭니다. 처리기는 클래스의 기본 클래스에서 동일한 이름의 모든 처리기를 "재정의"합니다.  
  
 이부 경우에는 기본 클래스 및 Windows가 해당 메시지에 대해 작업을 수행할 수 있도록 처리기가 기본 클래스에서 재정의된 처리기를 호출해야 합니다. 재정의에서 기본 클래스 처리기를 호출 하는 위치는 상황에 따라 달라집니다. 경우에 따라 기본 클래스 처리기를 먼저 호출하거나, 마지막으로 호출해야 합니다. 메시지를 직접 처리하지 않도록 선택한 일부 경우에는 기본 클래스 처리기를 조건에 따라 호출합니다. 또한 기본 클래스 처리기를 호출한 후, 기본 클래스 처리기에서 반환된 값 또는 상태에 따라 고유 처리기 코드를 조건에 따라 실행해야 할 수도 있습니다.  
  
> [!CAUTION]
>  인수를 기본 클래스 처리기에 전달하려는 경우에는 처리기에 전달된 인수를 수정하는 것이 안전하지 않습니다. 예를 들어 `nChar` 처리기의 `OnChar` 인수를 수정하려고 시도할 수 있습니다(대문자로 변환 등을 위해). 이 동작은 상당히 불분명 하지만이 효과 달성 하는 경우 사용 된 `CWnd` 멤버 함수 **SendMessage** 대신 합니다.  
  
 속성 창 지정된 된 메시지에 대 한 처리기 함수의 기초를 작성 하는 경우 지정된 된 메시지를 재정의 하는 적절 한 방법은 어떻게 결정 할까요-는 `OnCreate` 에 대 한 처리기 `WM_CREATE`, 예를 들어-권장의 형태로 스케치 합니다 멤버 함수를 재정의 합니다. 다음 예제에서는는 처리기 먼저 기본 클래스 처리기를 호출 하 고 계속만 조건 이라는-1을 반환 하지 않는 것이 좋습니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]  
  
 일반적으로 이러한 처리기의 이름은 접두사 "On"으로 시작합니다. 이러한 처리기 중 일부는 인수를 사용하지 않으며, 다른 일부는 인수를 사용합니다. 또한 일부 처리기는 `void` 이외의 반환 형식을 갖습니다. 모든에 대 한 기본 처리기 **WM_** 메시지에 설명 되어는 *MFC 참조* 클래스의 멤버 함수로 `CWnd` 이름이 "On."로 시작 멤버 함수 선언에 `CWnd` 접두사로 **afx_msg**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
