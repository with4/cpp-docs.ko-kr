---
title: "바닥 없는 Rich Edit 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8a92b180ed44937c29cd880dea7439e0cfe20b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bottomless-rich-edit-controls"></a>바닥 없는 Rich Edit 컨트롤
응용 프로그램 rich edit 컨트롤 크기를 조정할 수 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))은 항상 해당 콘텐츠와 동일한 크기가 되도록 필요에 따라 합니다. Rich edit 컨트롤의 부모 창에 전송 하 여이 이른바 "바닥 없음" 기능을 지원 한 [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) 해당 콘텐츠의 크기가 변경 될 때마다 알림 메시지입니다.  
  
 처리 하는 경우는 **EN_REQUESTRESIZE** 알림 메시지를 응용 프로그램에서 지정 된 차원으로 컨트롤 크기를 조정 해야 [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) 구조입니다. 응용 프로그램은 높이에서의 컨트롤 변경 사항을 수용하기 위해 컨트롤 근처의 모든 정보를 이동할 수 있습니다. 컨트롤의 크기를 조정 하려면 사용할 수 있습니다는 `CWnd` 함수 [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)합니다.  
  
 바닥 없음 rich edit 컨트롤을 강제로 실행할 수 있습니다는 **EN_REQUESTRESIZE** 를 사용 하 여 알림 메시지는 [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) 멤버 함수입니다. 이 메시지에 유용할 수 있습니다는 [OnSize](../mfc/reference/cwnd-class.md#onsize) 처리기입니다.  
  
 받을 **EN_REQUESTRESIZE** 알림 메시지를 사용 하 여 알림을 활성화 해야는 `SetEventMask` 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

