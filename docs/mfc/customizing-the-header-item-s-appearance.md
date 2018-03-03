---
title: "헤더 항목 &#39; 사용자 지정 모양을 s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dacb5cc7aa1c6d7c74a07ee911c5887efe1d877b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-the-header-item39s-appearance"></a>헤더 항목 &#39; 사용자 지정 s 모양
설정 하 여는 *dwStyle* 헤더 컨트롤을 처음 만들 때 매개 변수 ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), 모양을 정의할 수 있습니다 및 머리글의 동작 항목 또는 헤더의 자체를 제어 합니다.  
  
 샘플을 설정할 수 있습니다, 스타일 및 각각의 용도 다음과 같습니다.  
  
-   누름 같습니다 헤더 항목으로 사용 된 `HDS_BUTTONS` 스타일입니다.  
  
     Microsoft Outlook에서 하는 것 처럼 특정 열에 의해 데이터 정렬 등의 헤더 항목에 대해 마우스 클릭에 대 한 응답으로 작업을 수행 하려는 경우에이 스타일을 사용 합니다.  
  
-   헤더 항목 "핫 트래킹을" 모양 위로 마우스 커서를 가져갈 때, 사용 된 `HDS_HOTTRACK` 스타일입니다.  
  
     그렇지 않으면 플랫의 항목 위에 포인터를 움직이면 3D 개요를 표시 하는 핫 트래킹을 모음입니다.  
  
-   헤더 컨트롤은 숨겨야 나타내려면 사용은 `HDS_HIDDEN` 스타일입니다.  
  
     `HDS_HIDDEN` 스타일 헤더 컨트롤은 데이터 컨테이너 및 시각적 컨트롤이 아닌로 사용 하도록 나타냅니다. 이 스타일 컨트롤은 자동으로 숨겨지지 않습니다 되지만 대신의 동작에 영향을 `CHeaderCtrl::Layout`합니다. 에 반환 된 값의 **cy** 의 멤버는 `WINDOWPOS` 구조는 0이 됩니다 나타내는 컨트롤은 사용자에 게 표시할 수 없습니다.  
  
 이러한 속성에 대 한 자세한 내용은 참조 [항목](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows sdk에서입니다. 헤더 컨트롤에 항목을 추가 하는 방법에 대 한 정보를 참조 하십시오. [헤더 컨트롤에 항목 추가](../mfc/adding-items-to-the-header-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

