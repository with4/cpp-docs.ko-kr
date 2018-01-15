---
title: "클립보드: Windows 클립보드 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6063a27495d46e4b54f3133b92689e4b0faaa631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-windows-clipboard"></a>클립보드: Windows 클립보드 사용
이 항목에서는 MFC 응용 프로그램 내에서 표준 Windows 클립보드 API를 사용 하는 방법을 설명 합니다.  
  
 Windows에 대 한 대부분의 응용 프로그램 잘라내기 또는 데이터를 Windows 클립보드에 복사한 다음 붙여 클립보드의에서 데이터를 지원 합니다. 응용 프로그램 간에 클립보드 데이터 형식 달라 집니다. 프레임 워크 클래스 수가 제한에 대 한 제한 된 수의 클립보드 형식 지원 합니다. 클립보드 관련 명령을 정상적으로 구현 합니다-잘라내기, 복사 및 붙여넣기를 보기에 대 한 편집 메뉴에서 합니다. 클래스 라이브러리는 이러한 명령에 대 한 명령 Id 정의: **ID_EDIT_CUT**, **ID_EDIT_COPY**, 및 **ID_EDIT_PASTE**합니다. 해당 메시지 줄 프롬프트 정의 됩니다.  
  
 [프레임 워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md) 메뉴 명령 처리기 함수에 매핑하는 방법으로 응용 프로그램에서 메뉴 명령을 처리 하는 방법에 설명 합니다. 응용 프로그램 편집 메뉴에서 클립보드 명령에 대 한 처리기 함수를 정의 하지 않습니다,으로 사용할 수 없는 유지 합니다. 잘라내기 및 복사 명령에 대 한 처리기 함수를 작성 하려면 응용 프로그램에서 선택 영역을 구현 합니다. 붙여넣기 명령에 대 한 처리기 함수를 작성, 클립보드 인지 확인 형식으로 데이터를에서 응용 프로그램에 사용할 수 있습니다. 예를 들어 복사 명령을 사용 하려면 작성할 수 있습니다는 처리기 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 잘라내기, 복사 및 붙여넣기 명령을 경우 특정 상황 에서만 선택한 항목이 클립보드에 붙여넣기 명령을 어떤 경우에이 경우에 잘라내기 / 복사 명령은 사용 하도록 설정 해야 합니다. 컨텍스트에 따라 이러한 명령을 사용할지 여부를 지정 하는 업데이트 처리기 함수를 정의 하 여이 동작을 제공할 수 있습니다. 자세한 내용은 참조 [사용자 인터페이스 개체 업데이트 하는 방법을](../mfc/how-to-update-user-interface-objects.md)합니다.  
  
 Microsoft Foundation Class 라이브러리는 클립보드 지원을 사용 하 여 텍스트 편집에 대 한 제공 된 `CEdit` 및 `CEditView` 클래스입니다. OLE 클래스는 또한 OLE 항목을 포함 하는 구현 클립보드 작업을 단순화 합니다. OLE 클래스에 대 한 자세한 내용은 참조 하십시오. [클립보드: OLE 클립보드 메커니즘을 사용 하 여](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)합니다.  
  
 메뉴 명령, 실행 취소 같은 편집 다른 구현 (**ID_EDIT_UNDO**) 및 다시 실행 (**ID_EDIT_REDO**), 문서를 참조도 됩니다. 응용 프로그램에서 이러한 명령을 지원 하지 않는 경우 쉽게 삭제할 수 있습니다 이러한 Visual c + + 리소스 편집기를 사용 하 여 리소스 파일에서.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## <a name="see-also"></a>참고 항목  
 [클립보드](../mfc/clipboard.md)

