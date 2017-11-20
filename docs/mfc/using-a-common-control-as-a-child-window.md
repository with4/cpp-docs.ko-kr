---
title: "공용 컨트롤을 사용 하 여 자식 창으로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 116b844f9ecc270d31fe3731c38a63e64b2541fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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

