---
title: "확장 된 콤보 상자 컨트롤 만들기 | Microsoft Docs"
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
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80c3dc06ff391d1a90342f867813f60f9ce85bd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-extended-combo-box-control"></a>확장된 콤보 상자 컨트롤 만들기
확장 된 콤보 상자 컨트롤을 만들 방법을 대화 상자에서 컨트롤 사용 또는 비 모달 창에서 만드는 인지에 따라 달라 집니다.  
  
### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx 대화 상자에서 직접 사용 하려면  
  
1.  대화 상자 편집기에서 대화 상자 템플릿 리소스에는 확장 된 콤보 상자 컨트롤을 추가 합니다. 해당 컨트롤 ID를 지정합니다.  
  
2.  확장 된 콤보 상자 컨트롤의 속성 대화 상자를 사용 하 여 필요한 스타일을 지정 합니다.  
  
3.  사용 하 여는 [멤버 변수 추가 마법사](../ide/adding-a-member-variable-visual-cpp.md) 형식의 멤버 변수를 추가 하려면 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) 컨트롤 속성을 사용 합니다. 이 멤버를 사용하여 `CComboBoxEx` 멤버 함수를 호출할 수 있습니다.  
  
4.  속성 창을 사용 하 여 처리 해야 할 모든 확장 된 콤보 상자 컨트롤 알림 메시지에 대 한 대화 상자 클래스에 대 한 처리기 함수를 매핑합니다 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 설정에 대 한 추가 스타일의 `CComboBoxEx` 개체입니다.  
  
### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>CComboBoxEx 비 모달 창에서 사용 하려면  
  
1.  뷰 또는 창 클래스에서 컨트롤을 정의합니다.  
  
2.  컨트롤의 호출 [만들기](../mfc/reference/ctabctrl-class.md#create) 멤버 함수를 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)부모 창의 만큼, [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 처리기 함수입니다. 컨트롤의 스타일을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)

