---
title: 마법사 역할을 속성 시트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634359763f24e02987664fe3de1094e3e7fec64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347333"
---
# <a name="property-sheets-as-wizards"></a>마법사 역할을 하는 속성 시트
마법사 속성 시트의 주요 특징은 탐색 탭 대신 다음 또는 다시, 완료 및 취소 단추와 함께 제공 됩니다. 호출 해야 [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) 호출 하기 전에 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 에이 기능을 활용 하려면 속성 시트 개체입니다.  
  
 사용자에 게 동일한 [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) 및 [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) 한 페이지에서 다른 페이지로 이동 하는 동안 알림입니다. 다음과 마침 단추는 함께 사용할 수 없는 컨트롤입니다. 즉, 한 번에 둘 중 하나만 표시 됩니다. 첫 번째 페이지에서 다음 단추를 사용 해야 합니다. 마지막 페이지에서 사용자가을 하는 경우 "마침" 단추를 사용 해야 합니다. 이렇게 하지 않으면 자동으로 프레임 워크에서. 호출 해야 [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) 이를 위해 마지막 페이지에 있습니다.  
  
 모든 기본 단추를 표시 하려면 모두 "마침" 단추를 표시 하 고 단추를 이동 합니다. 다음 단추를 상대 위치 유지 되도록 뒤로 단추를 이동 합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)

