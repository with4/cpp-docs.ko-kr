---
title: 진행률 컨트롤에 대 한 설정을 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26afdcb58a64f2d2042596349acc4496aa530468
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="settings-for-the-progress-control"></a>진행률 컨트롤에 대한 설정
진행률 컨트롤에 대 한 기본 설정 ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md))은 범위 및 현재 위치입니다. 범위는 작업의 전체 기간을 나타냅니다. 현재 위치 하 응용 프로그램이 작업을 완료 했는지 진행 상황을 나타냅니다. 범위 또는 위치를 변경 하면는 진행률 컨트롤을 다시 그리도록 합니다.  
  
 기본적으로 설정 되어 범위 0-100 개이며 처음 위치가 0으로 설정 됩니다. 진행률 컨트롤에 대 한 현재 범위 설정을 검색 하려면 사용 된 [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) 멤버 함수입니다. 사용 하 여 범위를 변경 하려면는 [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) 멤버 함수입니다.  
  
 위치를 설정 하려면 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)합니다. 새 값을 지정 하지 않고 현재 위치를 검색 하려면 사용 [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)합니다. 예를 들어 다음 단순히 현재 작업의 상태를 쿼리 하는 것이 좋습니다.  
  
 단계는 진행률 컨트롤의 현재 위치를 사용 하 여 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)합니다. 각 단계의 크기를 설정 하려면 [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>참고 항목  
 [CProgressCtrl 사용](../mfc/using-cprogressctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

