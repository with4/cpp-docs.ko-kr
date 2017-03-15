---
title: "도구 설명 컨트롤에 대한 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "도구 설명[C++], 활성화"
  - "CToolTipCtrl 클래스, 설정"
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 도구 설명 컨트롤에 대한 설정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

도구 설명 컨트롤\([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)\)을 활성 또는 비활성으로 설정할 수 있습니다. 활성으로 설정하는 경우 커서로 도구를 가리키면 도구 설명 컨트롤이 나타납니다. 비활성으로 설정하는 경우 커서로 도구를 가리켜도 도구 설명 컨트롤이 나타나지 않습니다. 도구 설명 컨트롤을 활성화 또는 비활성화하려면 [활성화](../Topic/CToolTipCtrl::Activate.md)를 호출합니다.  
  
 도구 설명 컨트롤의 소유자 창이 활성 또는 비활성 상태인지에 관계없이 **TTS\_ALWAYSTIP** 스타일을 사용하여 커서로 도구를 가리킬 때 도구 설명을 표시하도록 활성 도구 설명을 설정할 수 있습니다. 이 스타일을 사용하지 않을 경우 도구의 소유자 창이 활성 상태이면 도구 설명 컨트롤이 나타나지만 비활성 상태이면 나타나지 않습니다.  
  
 대부분의 응용 프로그램에는 메뉴 명령에 해당하는 도구를 포함하는 도구 모음이 있습니다. 이러한 도구의 경우 도구 설명 컨트롤이 해당 메뉴 항목과 동일한 텍스트를 표시하는 것이 편리합니다. 컨트롤에 **TTS\_NOPREFIX** 스타일이 없을 경우 도구 설명 컨트롤에 전달된 모든 문자열에서 앰퍼샌드\(&\) 액셀러레이터 문자가 자동으로 제거됩니다.  
  
## 참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)