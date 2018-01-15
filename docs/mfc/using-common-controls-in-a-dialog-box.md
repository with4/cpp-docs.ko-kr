---
title: "공용 컨트롤을 사용 하 여 대화 상자에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67a9c77e6a8e5721bca6e3741b4b337cfdb42393
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-common-controls-in-a-dialog-box"></a>대화 상자에서 공용 컨트롤 사용
Windows 공용 컨트롤에서 사용할 수 있습니다 [대화 상자](../mfc/dialog-boxes.md), 폼 뷰, 레코드 뷰 및 대화 상자 템플릿을 기반으로 하는 다른 창. 약간의 다른 점이 있지만 다음 절차는 폼에서도 작동합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-use-a-common-control-in-a-dialog-box"></a>대화 상자에서 공용 컨트롤을 사용하려면  
  
1.  대화 상자 템플릿에 컨트롤을 배치 [대화 상자 편집기를 사용 하 여](../mfc/using-the-dialog-editor-to-add-controls.md)합니다.  
  
2.  컨트롤을 나타내는 멤버 변수를 대화 상자 클래스에 추가합니다. 에 **멤버 변수 추가** 대화 상자에서 확인 **제어 변수** 는 및 **제어** 에 대해 선택 된는 **범주**합니다.  
  
3.  공용 컨트롤이 프로그램에 입력을 제공하는 경우, 대화 상자 클래스에서 추가 멤버 변수를 선언하여 해당 입력 값을 처리합니다.  
  
    > [!NOTE]
    >  클래스 뷰에서 상황에 맞는 메뉴를 사용 하 여 이러한 멤버 변수를 추가할 수 있습니다 (참조 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)).  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 대화 상자 클래스에 대 한 공용 컨트롤에 대 한 초기 조건을 설정 합니다. 이전 단계에서 만든 멤버 변수를 사용하여 멤버 함수를 통해 초기 값 및 기타 설정을 지정합니다. 설정에 대한 자세한 내용은 컨트롤에 대한 다음 설명을 참조하십시오.  
  
     사용할 수도 있습니다 [대화 상자 데이터 교환](../mfc/dialog-data-exchange-and-validation.md) (DDX) 대화 상자에서 컨트롤을 초기화 합니다.  
  
5.  대화 상자의 컨트롤에 대한 처리기에서 멤버 변수를 사용해서 컨트롤을 조작합니다. 메서드에 대한 자세한 내용은 컨트롤에 대해 다음 설명을 참조하십시오.  
  
    > [!NOTE]
    >  멤버 변수는 대화 상자 자체가 있는 경우에만 존재합니다. 대화 상자가 닫힌 다음에는 컨트롤에서 입력 값을 쿼리할 수 없습니다. 공용 컨트롤의 입력 값을 사용하려면 대화 상자 클래스에서 `OnOK`를 재정의합니다. 재정의 시, 컨트롤에서 입력 값을 쿼리하고 해당 값을 대화 상자 클래스의 멤버 변수에 저장합니다.  
  
    > [!NOTE]
    >  또한 대화 상자 데이터 교환을 사용해서 대화 상자에 있는 컨트롤에서 값을 설정하거나 검색할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 일부 공용 컨트롤을 대화 상자에 추가하면 대화 상자가 더 이상 작동하지 않습니다. 참조 [대화 상자에 컨트롤 추가 대화 상자에 상자가 더 이상 작동](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) 방법은 이러한 상황을 처리 합니다.  
  
## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요  
  
-   [컨트롤에 추가 대화 상자를 직접 대신 대화 상자 편집기](../mfc/adding-controls-by-hand.md)  
  
-   [표준 Windows 공용 컨트롤 중 하나에서 내 컨트롤 파생](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [공용 컨트롤을 사용 하 여 자식 창으로](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [컨트롤에서 알림 메시지 받기](../mfc/receiving-notification-from-common-controls.md)  
  
-   [대화 상자 데이터 교환 (DDX)를 사용 하 여](../mfc/dialog-data-exchange-and-validation.md)  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)

