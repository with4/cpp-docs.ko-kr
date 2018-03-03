---
title: "확장 된 콤보 상자 컨트롤에서 알림 메시지 처리 | Microsoft Docs"
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
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a78e7b9fd8f9c67f14a4bb51088866785d372cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>확장된 콤보 상자 컨트롤에서 알림 메시지 처리
사용자가 확장된 콤보 상자를 조작하면 컨트롤(`CComboBoxEx`)이 해당 부모 창(일반적으로 뷰 또는 대화 상자 개체)에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 드롭다운 목록을 활성화하거나 컨트롤의 편집 상자를 클릭하면 **CBEN_BEGINEDIT** 알림이 전송됩니다.  
  
 속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.  
  
 다음 목록에서는 확장된 콤보 상자 컨트롤에서 전송되는 다양한 알림에 대해 설명합니다.  
  
-   **CBEN_BEGINEDIT** 사용자가 드롭다운 목록을 활성화하거나 컨트롤의 편집 상자를 클릭하면 전송됩니다.  
  
-   **CBEN_DELETEITEM** 항목이 삭제된 경우 전송됩니다.  
  
-   **CBEN_DRAGBEGIN** 사용자가 컨트롤의 편집 부분에 표시된 항목의 이미지를 끌기 시작하면 전송됩니다.  
  
-   **CBEN_ENDEDIT** 사용자가 편집 상자 내에서 작업을 완료하거나 컨트롤의 드롭다운 목록에서 항목을 선택한 경우 전송됩니다.  
  
-   **CBEN_GETDISPINFO** 콜백 항목에 대한 표시 정보를 검색하기 위해 전송됩니다.  
  
-   **CBEN_INSERTITEM** 컨트롤에 새 항목이 삽입된 경우 전송됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComboBoxEx 사용](../mfc/using-ccomboboxex.md)   
 [컨트롤](../mfc/controls-mfc.md)

