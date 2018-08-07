---
title: 메시지 맵의 찾을 장소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19dfaec7d97bed560665fce25c2ddf2cc816a483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383395"
---
# <a name="where-to-find-message-maps"></a>메시지 맵을 찾을 장소
응용 프로그램 마법사로 새로운 기초 응용 프로그램을 만들 때 응용 프로그램 마법사를 생성 하는 각 명령 대상 클래스에 대 한 메시지 맵을 작성 합니다. 파생된 응용 프로그램, 문서, 뷰 및 프레임 창 클래스를 포함 합니다. 이러한 메시지 맵 중 일부 특정 메시지와 미리 정의 된 명령에 대 한 응용 프로그램 마법사에서 제공 하는 항목은 이미 고 추가할 처리기에 대 한 자리 표시자 일 뿐입니다.  
  
 클래스의 메시지 맵을에 위치한는 합니다. 클래스에 대 한 CPP 파일입니다. 메시지 및 처리 하는 각 클래스는 명령에 대 한 항목을 추가 하려면 속성 창을 사용 응용 프로그램 마법사에서 생성 하는 기본 메시지 맵 작업, 있습니다. 일부 항목을 추가 하면 일반적인 메시지 맵에 다음 같을 수 있습니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 메시지 맵 매크로의 컬렉션으로 구성 됩니다. 두 매크로 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 및 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)을 메시지 맵에 묶습니다. 다른 매크로 같은 `ON_COMMAND`, 메시지 맵의 내용을 입력 합니다.  
  
> [!NOTE]
>  메시지 맵 매크로 세미콜론으로 따르지 합니다.  
  
 클래스 추가 마법사를 사용 하 여 새 클래스를 만들 때 클래스에 대 한 메시지 맵을 제공 합니다. 또는 메시지 맵 소스 코드 편집기를 사용 하 여 수동으로 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)

