---
title: "메시지 맵 매크로 (MFC) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f890e0675be58c8e20e313bea54b4145e2ce0bf3
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-mfc"></a>메시지 맵 매크로(MFC)
MFC는 메시지 맵을 지원 하기 위해 다음과 같은 매크로 제공 합니다.  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>메시지 맵 선언 및 구분 매크로  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](http://msdn.microsoft.com/library/c225e7e0-a81b-495c-97f9-3e0aa1f65036)|메시지 맵 (클래스 선언에 사용 해야 합니다) 함수에 메시지를 매핑하기 위해 클래스에서 사용될지를 선언 합니다.|  
|[BEGIN_MESSAGE_MAP](http://msdn.microsoft.com/library/d9201e18-04e0-4639-9810-f15768627fc2)|메시지 맵 (클래스 구현에 사용 해야 합니다)의 정의 시작 합니다.|  
|[END_MESSAGE_MAP](http://msdn.microsoft.com/library/40f611f1-a3b4-4097-b683-091bf7cfab8b)|메시지 맵 (클래스 구현에 사용 해야 합니다)의 정의 끝냅니다.|  
  
### <a name="message-mapping-macros"></a>메시지 매핑 매크로  
  
|||  
|-|-|  
|[ON_COMMAND](http://msdn.microsoft.com/library/f24f8bda-2cf4-49d5-aa3d-6f2e6bb003f2)|함수는 지정 된 명령 메시지를 처리 하는 것을 나타냅니다.|  
|[ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)|함수는 지정 된 컨트롤 알림 메시지를 처리 하는 것을 나타냅니다.|  
|[ON_MESSAGE](http://msdn.microsoft.com/library/e2faeb13-9f6e-4c0d-9f6d-b2e141a0db1e)|함수는 사용자 정의 메시지를 처리할지를 나타냅니다.|  
|[ON_OLECMD](http://msdn.microsoft.com/library/6c86327c-3d48-42ac-9dae-e0ccd3a81793)|DocObject 또는 해당 컨테이너에서 메뉴 명령을 처리할 함수를 나타냅니다.|  
|[ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d)|함수에서 등록 된 사용자 정의 메시지를 처리할지를 나타냅니다.|  
|[ON_REGISTERED_THREAD_MESSAGE](http://msdn.microsoft.com/library/3f598bc2-b2f0-410f-8ba0-7714502170f3)|어떤 함수가 있는 경우 등록 된 사용자 정의 메시지를 처리할지 나타냅니다는 `CWinThread` 클래스입니다.|  
|[ON_THREAD_MESSAGE](http://msdn.microsoft.com/library/f718f47a-d5b1-4514-914b-e3fe2d919003)|함수를 사용자 정의 메시지를 처리할 경우 나타냅니다는 `CWinThread` 클래스입니다.|  
|[ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)|함수는 지정 된 사용자 인터페이스 업데이트 명령 메시지를 처리할지를 나타냅니다.|  
  
### <a name="message-map-range-macros"></a>메시지 맵 범위 매크로  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)|함수 매크로에 처음 두 매개 변수에 지정 된 명령 Id의 범위를 처리할지를 나타냅니다.|  
|[ON_UPDATE_COMMAND_UI_RANGE](http://msdn.microsoft.com/library/b7105bf1-44ad-4b00-b947-31478f964729)|업데이트 처리기를 매크로에 처음 두 매개 변수에 지정 된 명령 Id의 범위를 처리할지를 나타냅니다.|  
|[ON_CONTROL_RANGE](http://msdn.microsoft.com/library/46f0e1bb-569b-4b8b-9b80-89701d1cd7fd)|함수에서 컨트롤 매크로에 두 번째 및 세 번째 매개 변수에 지정 된 Id의 범위에서 알림을 처리할지를 나타냅니다. 첫 번째 매개 변수는 컨트롤 알림 메시지를와 같은 **BN_CLICKED**합니다.|  
  
 메시지 맵, 메시지 맵 선언 및 구분 매크로 및 메시지 매핑 매크로에 대 한 자세한 내용은 참조 하십시오. [메시지 맵](../../mfc/reference/message-maps-mfc.md) 및 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다. 메시지 맵 범위에 대 한 자세한 내용은 참조 [메시지 맵 범위에 대 한 처리기](../../mfc/handlers-for-message-map-ranges.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메시지 맵](../../mfc/reference/message-maps-mfc.md)



