---
title: CSpinButtonCtrl 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03b1e83977c1d75070e8878dfdcc53c7afca7a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl 사용
*스핀 단추* 컨트롤 (라고도 *위쪽 / 아래쪽* 제어)는 쌍의 화살표는 값을 조정 하기 위해 클릭할 수를 제공 합니다. 이 값 이라고는 *현재 위치*합니다. 위치는 스핀 단추 범위 내에 유지 합니다. 위쪽 화살표를 클릭 위치 최대;으로 이동 고 위치 최소를 향해 이동 사용자가 있는 아래쪽 화살표를 클릭 합니다.  
  
 스핀 단추 컨트롤에서 MFC에서 표시 되는 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) 클래스입니다.  
  
> [!NOTE]
>  기본적으로 스핀 단추에 대 한 범위에 영 (0)로 설정 하는 최대 및 최소 100으로 설정 합니다. 최대값은 최소값 보다 작을 이기 때문에 위쪽 화살표를 클릭 하 위치 줄어들고 늘립니다 아래쪽 화살표를 클릭 합니다. 사용 하 여 [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 이러한 값을 조정 해야 합니다.  
  
 일반적으로 현재 위치 도우미 컨트롤에 표시 됩니다. 도우미 제어 라고는 *버디 창*합니다. 스핀 단추 컨트롤의 예시의 경우에 대 한 참조 [Up-down 컨트롤에 대 한](http://msdn.microsoft.com/library/windows/desktop/bb759889) Windows sdk에서입니다.  
  
 Spin 컨트롤 및 편집 컨트롤 버디 창의 Visual Studio에서을 만들려면 먼저 대화 상자 또는 창에 편집 컨트롤을 끌어 놓은 다음 spin 컨트롤을 끕니다. Spin 컨트롤을 선택 하 고 설정의 **Auto Buddy** 및 **Buddy Integer 설정** 속성을 **True**합니다. 설정의 **맞춤** 속성 **오른쪽 맞춤** 가장 일반적입니다. 이러한 설정을 사용 하 여 바로 편집 컨트롤 탭 순서에서 앞에 오는 때문에 편집 컨트롤은 버디 창으로 설정 됩니다. 편집 컨트롤은 정수를 표시 하 고 spin 컨트롤 편집 컨트롤의 오른쪽에 포함 되어 있습니다. 필요에 따라 spin 컨트롤의 유효한 범위를 사용 하 여 설정할 수 있습니다는 [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 메서드. 이벤트 처리기가 없는 직접 데이터를 교환 하기 때문에 spin 컨트롤와 버디 창 간의 통신에 필요 합니다. 다른 용도로 spin 컨트롤을 사용 하는 경우 예를 들어 페이징 하는 일련의 windows 또는 대화 상자에 다음 추가 대 한 처리기는 `UDN_DELTAPOS` 메시지 보내기 및 사용자 지정 작업을 수행 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [스핀 단추 스타일](../mfc/spin-button-styles.md)  
  
-   [스핀 단추 멤버 함수](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤](../mfc/controls-mfc.md)

