---
title: CToolTipCtrl을 사용 하 여 CToolTipCtrl 개체 만들기 및 조작에 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2143ea37cfe9448e43aacfa75622beab93d2fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382336"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl을 사용하여 CToolTipCtrl 개체 만들기 및 조작
예로 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) 사용:  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>CToolTipCtrl을 만들고 조작하려면  
  
1.  `CToolTipCtrl` 개체를 생성합니다.  
  
2.  호출 [만들기](../mfc/reference/ctooltipctrl-class.md#create) Windows 도구 설명 공용 컨트롤을 만들고에 연결 하는 `CToolTipCtrl` 개체입니다.  
  
3.  호출 [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) 에 도구 설명 컨트롤은 도구에 커서를 가져갈 때 도구 설명에 저장 된 정보가 표시 되도록 도구 등록 합니다.  
  
4.  호출 [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) 도구에 대 한 유지 관리 도구 설명 정보를 설정 합니다.  
  
5.  호출 [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) 도구에 대 한 새로운 경계 사각형을 설정 합니다.  
  
6.  호출 [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) 지정 된 도구의 경계 사각형 내 여부와 그럴 경우를 결정 하는 지점, 테스트 하는 도구에 대 한 정보를 검색 합니다.  
  
7.  호출 [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) 도구의 수를 검색 하 여 도구 설명 컨트롤에 등록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

