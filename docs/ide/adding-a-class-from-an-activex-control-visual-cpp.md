---
title: ActiveX 컨트롤의 클래스 추가(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 793adf38da33808371a0df71f671c3e29da75326
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33322408"
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX 컨트롤의 클래스 추가(Visual C++)
이 마법사를 사용하여 사용 가능한 ActiveX 컨트롤의 인터페이스에서 MFC 클래스를 만듭니다. MFC 클래스를 [MFC 응용 프로그램](../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md) 또는 [MFC ActiveX 컨트롤](../mfc/reference/creating-an-mfc-activex-control.md)에 추가할 수 있습니다.  
  
> [!NOTE]
>  ActiveX 컨트롤에서 클래스를 추가하기 위해 자동화가 활성화된 MFC 프로젝트를 만들 필요가 없습니다.  
  
 ActiveX 컨트롤은 다양한 OLE 기능을 지원하고 많은 소프트웨어 요구 사항에 맞게 사용자 지정할 수 있는 COM(구성 요소 개체 모델)을 기반으로 재사용 가능한 소프트웨어 구성 요소입니다. ActiveX 컨트롤은 일반적인 ActiveX 컨트롤 컨테이너와 인터넷의 World Wide Web 페이지 모두에 사용할 수 있도록 디자인되었습니다.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX 컨트롤에서 MFC 클래스를 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 ActiveX 컨트롤 클래스를 추가할 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음, **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ActiveX 컨트롤의 MFC 클래스**를 클릭한 다음, **열기**를 클릭하여 [ActiveX 컨트롤에서 클래스 추가 마법사](../ide/add-class-from-activex-control-wizard.md)를 표시합니다.  
  
 이 마법사에서 ActiveX 컨트롤의 인터페이스 여러 개를 추가할 수 있습니다. 마찬가지로, 단일 마법사 세션에서 ActiveX 컨트롤 여러 개의 클래스를 만들 수 있습니다.  
  
 시스템에 등록된 ActiveX 컨트롤에서 클래스를 추가하거나, 시스템에 처음 등록하지 않고도 형식 라이브러리 파일(.tlb, .olb, .dll, .ocx 또는 .exe)에 있는 ActiveX 컨트롤에서 클래스를 추가할 수 있습니다. ActiveX 컨트롤 등록에 대한 자세한 내용은 [OLE 컨트롤 등록](../mfc/reference/registering-ole-controls.md)을 참조하세요.  
  
 마법사는 선택한 ActiveX 컨트롤에서 추가한 각 인터페이스에 대해 [CWnd](../mfc/reference/cwnd-class.md) 또는 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)에서 파생된 MFC 클래스를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [COM 및 ATL 소개](../atl/introduction-to-com-and-atl.md)