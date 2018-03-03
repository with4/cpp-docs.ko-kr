---
title: "MFC ActiveX 컨트롤: 스톡 메서드 추가 | Microsoft Docs"
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
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2531f84974626fcdb364df67b12f27d61e75a62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX 컨트롤: 스톡 메서드 추가
스톡 메서드가 사용자 지정 메서드 점에서 다릅니다 클래스에 의해 이미 구현 [COleControl](../mfc/reference/colecontrol-class.md)합니다. 예를 들어 `COleControl` 컨트롤에 대 한 새로 고침 메서드를 지원 하는 미리 정의 된 멤버 함수를 포함 합니다. 이 스톡 메서드가 대 한 디스패치 맵 항목이 **DISP_STOCKFUNC_REFRESH**합니다.  
  
 `COleControl`스톡 두 가지 방법을 지원: DoClick 및 새로 고침 합니다. 새로 고침을 즉시 업데이트 하는 컨트롤의 모양을; 컨트롤의 사용자에 의해 호출 됩니다. DoClick 컨트롤의 Click 발생 하기 위해 호출 된 이벤트입니다.  
  
|메서드|디스패치 맵 항목|주석|  
|------------|------------------------|-------------|  
|`DoClick`|**DISP_STOCKPROP_DOCLICK)**|Click 이벤트를 발생 시킵니다.|  
|**새로 고침**|**DISP_STOCKPROP_REFRESH)**|컨트롤의 모양을 즉시 업데이트 됩니다.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a>사용 하 여 스톡 메서드 추가 메서드 추가 마법사  
 스톡 메서드 추가 하는 것은 간단를 사용 하 여 [메서드 추가 마법사](../ide/add-method-wizard.md)합니다. 다음 절차에서는 MFC ActiveX 컨트롤 마법사를 사용 하 여 만든 컨트롤에 Refresh 메서드를 추가 합니다.  
  
#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>스톡 메서드 추가 마법사를 사용 하 여 Refresh 메서드를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.  
  
3.  컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.  
  
4.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **메서드 추가**합니다.  
  
     메서드 추가 마법사가 열립니다.  
  
5.  에 **메서드 이름** 상자 **새로 고침**합니다.  
  
6.  **마침**을 클릭합니다.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a>스톡 메서드 추가 마법사 변경 메서드  
 스톡 Refresh 메서드 컨트롤의 기본 클래스에서 지원 되는 **메서드 추가 마법사** 컨트롤의 클래스 선언에는 전혀 변경 되지 않습니다. 컨트롤의 디스패치 지도 메서드에 대 한 항목을 추가 해당 합니다. IDL 파일입니다. 구현 되는 컨트롤의 디스패치 맵에 다음 줄 추가 됩니다 (합니다. Cpp) 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 이렇게 하면 컨트롤의 사용자에 게 사용할 수 있는 새로 고침 메서드가 있습니다.  
  
 다음 줄은 컨트롤의에 추가 됩니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 이 줄 Refresh 메서드 특정 ID 번호를 할당합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

