---
title: "일반 대화 상자 클래스 | Microsoft Docs"
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
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d76c387c9aa9f53f8503d3606b2b47cdb5c6be6d
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="common-dialog-classes"></a>일반 대화 상자 클래스
클래스 외에도 [CDialog](../mfc/reference/cdialog-class.md), MFC 여러 클래스에서 파생 된 제공 `CDialog` 다음 표와 같이 자주 사용 되는 대화 상자를 캡슐화 하 합니다. 캡슐화 된 대화 상자 "일반 대화 상자" 이라고 하며 일부 Windows 공용 대화 라이브러리 (COMMDLG 합니다. DLL)입니다. 버전 3.1 이상 Windows의 일부인 일반 대화 상자 템플릿 리소스 및 이러한 클래스에 대 한 코드 창에 제공 됩니다.  
  
### <a name="common-dialog-classes"></a>일반 대화 상자 클래스  
  
|파생 된 대화 상자 클래스|용도|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|색을 선택 하는 사용자 수 있습니다.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|사용자를를 열려면 또는 저장 하려면 파일 이름을 선택할 수 있습니다.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|시작 찾기 또는 바꾸기 작업을 텍스트 파일로 사용자 수 있습니다.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|글꼴을 지정 하는 사용자 수 있습니다.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|사용자를 인쇄 작업에 대 한 정보를 지정할 수 있습니다.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows의 인쇄 속성 시트입니다.|  
  
 일반 대화 상자 클래스에 대 한 자세한 내용은 참조에서 각 클래스 이름을 *MFC 참조*합니다. MFC는 또한 여러 OLE에 사용 되는 표준 대화 상자 클래스를 제공 합니다. 이러한 클래스에 대 한 정보에 대 한 기본 클래스를 참조 하십시오. [COleDialog](../mfc/reference/coledialog-class.md)에 *MFC 참조*합니다.  
  
 MFC의 다른 세 가지 클래스 대화 상자와 비슷한 특징을 갖습니다. 클래스에 대 한 내용은 [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)의 클래스를 참조는 *MFC 참조*합니다. 클래스에 대 한 내용은 [CDialogBar](../mfc/reference/cdialogbar-class.md), 참조 [대화 상자 모음](../mfc/dialog-bars.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)

