---
title: 공용 컨트롤을 사용 하 여 자식 창으로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50d21675d913211026a2077a0830b7d8ed1225c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-common-control-as-a-child-window"></a>공용 컨트롤을 자식 창으로 사용
다른 모든 창의 자식 창으로 사용할 수는 Windows 공용 컨트롤 중 하나입니다. 다음 절차에는 공용 컨트롤을 동적으로 만들고 다음 작업을 하는 방법을 설명 합니다.  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>공용 컨트롤을 자식 창으로 사용 하려면  
  
1.  관련된 클래스 또는 처리기에서 컨트롤을 정의 합니다.  
  
2.  컨트롤의 재정의 사용 하 여는 [CWnd::Create](../mfc/reference/cwnd-class.md#create) 메서드 Windows 컨트롤을 만들 수 있습니다.  
  
3.  컨트롤을 만든 후 (만큼는 `OnCreate` 처리기 경우 하위 컨트롤), 해당 멤버 함수를 사용 하 여 컨트롤을 조작할 수 있습니다. 개별 컨트롤의 설명을 참조 [컨트롤](../mfc/controls-mfc.md) 메서드에 대 한 자세한 내용은 합니다.  
  
4.  사용 하 여 컨트롤을 마쳤으면 [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) 컨트롤을 제거할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)

