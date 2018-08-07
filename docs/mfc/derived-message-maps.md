---
title: 메시지 맵 파생 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e780d411e62d1347d8286f86b45df864b0fcdb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342968"
---
# <a name="derived-message-maps"></a>파생된 메시지 맵
메시지 처리, 클래스의 메시지를 확인 하는 동안 맵이 메시지 맵 스토리의 끝 되었습니다. 어떻게 클래스 `CMyView` (에서 파생 된 `CView`)과 일치 하는 항목이 메시지에 대 한 없습니다  
  
 `CView`의 기본 클래스 `CMyView`에서 차례로 파생 `CWnd`합니다. 따라서 `CMyView` *은* 는 `CView` 및 *은* 는 `CWnd`합니다. 해당 클래스에 자신의 메시지 맵을 있습니다. "A" 뷰 계층 구조 아래에 유지 하지만 클래스의 계층 관계를 보여 줍니다.이 그림 다음에 유의 `CMyView` 개체는 세 클래스 모두의 특성을 가진 단일 개체입니다.  
  
 ![뷰 계층 구조](../mfc/media/vc38621.gif "vc38621")  
계층 구조 보기  
  
 클래스에서 메시지를 일치할 수 없습니다 따라서 `CMyView`의 프레임 워크가 메시지 맵을 이름과 기본 클래스의 메시지 맵을 검색 합니다. `BEGIN_MESSAGE_MAP` 매크로의 메시지 맵 시작 부분에 해당 인수로 두 클래스 이름을 지정 합니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]  
  
 첫 번째 인수는 메시지 맵을 속해 있는 클래스를 이름을 지정 합니다. 두 번째 인수는 직접 기본 클래스와의 연결을 제공- `CView` 여기-프레임 워크는 너무 자신의 메시지 맵을 검색할 수 있도록 합니다.  
  
 기본 클래스에서 제공 하는 메시지 처리기는 파생된 클래스에 의해 상속 되므로 됩니다. 이 가상 모든 처리기 멤버 함수를 만들 필요 없이 일반 가상 멤버 함수와 매우 비슷합니다.  
  
 처리기는 기본 클래스 메시지 맵 중 하나에서 발견 되 면 메시지의 기본 처리가 수행 됩니다. 메시지가 명령 경우 프레임 워크가 라우팅합니다. 그런 다음 명령 대상입니다. 표준 Windows 메시지 이면 메시지를 적절 한 기본 창 프로시저로 전달 됩니다.  
  
 메시지 맵 일치 하는 속도 프레임 워크는 동일한 메시지가 다시 받도록 가능성에 최근의 일치 항목을 캐시 합니다. 이는 프레임 워크 프로세스 메시지를 매우 효율적으로 처리 됩니다. 메시지 맵 공간-보다 더 효율적 가상 함수를 사용 하는 구현 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)

