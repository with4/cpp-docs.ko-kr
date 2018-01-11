---
title: "CToolBarCtrl 개체 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CToolBarCtrl
dev_langs: C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e86fad8191c4dea2eed3ae34ec96ed853ac1deae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl 개체 만들기
[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 여러 개의 내부 데이터 구조를 포함 하는 개체-단추 이미지 비트맵의 목록, 단추 레이블 문자열의 목록 및 목록이 `TBBUTTON` 구조-있는 이미지로 연결 및/또는 위치, 스타일, 상태를 포함 하는 문자열 및 단추의 명령 ID입니다. 각각의 이러한 데이터 구조 요소에서 참조 하는 0부터 시작 인덱스입니다. 사용 하기 전에 `CToolBarCtrl` 개체를 이러한 데이터 구조를 설정 해야 합니다. 목록이 데이터 구조에 대 한 참조 [도구 모음 컨트롤](controls-mfc.md) Windows sdk에서입니다. 단추 레이블;에 대 한 문자열 목록에만 사용할 수 있습니다. 도구 모음에서 문자열을 검색할 수 없습니다.  
  
 `CToolBarCtrl` 개체를 사용하려면, 일반적으로 다음 단계를 수행해야 합니다.  
  
### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl 개체를 사용 하려면  
  
1.  생성 된 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체입니다.  
  
2.  호출 [만들기](../mfc/reference/ctoolbarctrl-class.md#create) Windows 도구 모음 공용 컨트롤을 만들고에 연결 하는 `CToolBarCtrl` 개체입니다. 단추에 대 한 비트맵 이미지를 원하는 경우 추가 단추 비트맵 도구 모음으로 호출 하 여 [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap)합니다. 단추에 대 한 문자열 레이블을 원하는 경우 문자열을 추가한 도구 모음으로 호출 하 여 [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) 및/또는 [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings)합니다. 호출한 후 `AddString` 및/또는 `AddStrings`를 호출 해야 [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) 사용 하려면 문자열 또는 문자열을 표시 합니다.  
  
3.  호출 하 여 도구 모음 단추 구조 추가 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)합니다.  
  
4.  도구 설명 처리 **TTN_NEEDTEXT** 모음의 소유자 창에서 메시지에 설명 된 대로 [도구 팁 알림 처리](../mfc/handling-tool-tip-notifications.md)합니다.  
  
5.  사용자 도구 모음을 사용자 지정할 수 있게 되기를 원하는 경우 처리는 소유자 창에서 사용자 지정 알림 메시지에 설명 된 대로 [사용자 지정 알림 처리](../mfc/handling-customization-notifications.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

