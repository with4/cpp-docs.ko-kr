---
title: "ActiveX 컨트롤 (Visual c + +)에서 클래스를 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f059396c91ddb51247347d10e6c8f79a6c95522f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX 컨트롤의 클래스 추가(Visual C++)
이 마법사를 사용 하 여 사용 가능한 ActiveX 컨트롤의 인터페이스에서 MFC 클래스를 만듭니다. 에 MFC 클래스를 추가할 수는 [MFC 응용 프로그램](../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md), 또는 [MFC ActiveX 컨트롤](../mfc/reference/creating-an-mfc-activex-control.md)합니다.  
  
> [!NOTE]
>  ActiveX 컨트롤에서 클래스를 추가할 수 있도록 설정 하는 자동화가 포함 된 MFC 프로젝트를 만들 필요가 없습니다.  
  
 ActiveX 컨트롤은 다시 사용할 수 있는 소프트웨어 구성 요소를 COM을 기반으로 구성 요소 개체 모델 ()는 다양 한 OLE 기능을 지원 하 고 많은 소프트웨어 요구 사항에 맞게 사용자 지정할 수 있습니다. ActiveX 컨트롤은 일반적인 ActiveX 컨트롤 컨테이너와 World Wide web 웹 페이지에는 인터넷에서 사용 하기 위해 설계 되었습니다.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX 컨트롤의 MFC 클래스를 추가 하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), ActiveX 컨트롤 클래스를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 클릭 **추가**, 클릭 하 고 **클래스 추가**합니다.  
  
3.  에 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 클릭 **ActiveX 컨트롤의 MFC 클래스**, 클릭 하 고 **열려** 표시 하는 [ActiveX에서 클래스 추가 마법사 컨트롤](../ide/add-class-from-activex-control-wizard.md)합니다.  
  
 마법사에서 ActiveX 컨트롤에서 둘 이상의 인터페이스를 추가할 수 있습니다. 마찬가지로, 단일 마법사 세션에서 둘 이상의 ActiveX 컨트롤의 클래스를 만들 수 있습니다.  
  
 클래스에 추가 하 여 시스템에 등록 하는 ActiveX 컨트롤에서 또는 첫 번째 시스템에 등록 하지 않고 형식 라이브러리 파일 (.tlb,.olb,.dll,.ocx, 또는.exe)에 있는 ActiveX 컨트롤에서 클래스를 추가할 수 있습니다. 참조 [OLE 컨트롤 등록](../mfc/reference/registering-ole-controls.md) ActiveX 컨트롤 등록에 대 한 자세한 내용은 합니다.  
  
 마법사에서 파생 하는 MFC 클래스를 만듭니다. [CWnd](../mfc/reference/cwnd-class.md) 또는 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), 선택된 된 ActiveX 컨트롤에서 추가할 각 인터페이스에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)