---
title: COM 인터페이스 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.editing.interfaces
dev_langs:
- C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd7a61593a1024c00c0fd0de6bd62ff3ee9323b3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33338684"
---
# <a name="editing-a-com-interface"></a>COM 인터페이스 편집
클래스 뷰 바로 가기 메뉴의 명령을 사용하여 Visual C++ 프로젝트의 COM 인터페이스에 대한 새 메서드와 속성을 정의할 수 있습니다. 또한 도구 상자에서 ActiveX 컨트롤용 이벤트를 정의할 수 있습니다.  
  
 ATL 및 MFC 기반 COM 개체 클래스의 경우, 인터페이스를 편집하는 동시에 클래스 구현을 편집할 수 있습니다.  
  
> [!NOTE]
>  **클래스 추가** 대화 상자 외부에 정의한 인터페이스의 경우, Visual C++는 메서드 또는 속성을 .idl 파일에 추가하고, 인터페이스를 수동으로 추가한 경우에도 메서드를 구현하는 클래스에 스텁을 추가합니다.  
  
 다음 세 가지 마법사를 사용하여 기존 인터페이스를 사용자 지정할 수 있습니다. 클래스 뷰에서 사용할 수 있습니다.  
  
|마법사|프로젝트 형식|  
|------------|------------------|  
|[속성 추가 마법사](../ide/names-add-property-wizard.md)|ATL을 지원하는 ATL 또는 MFC 프로젝트. 속성을 추가할 인터페이스를 마우스 오른쪽 단추로 클릭합니다.<br /><br /> Visual C++가 프로젝트 형식을 검색하고 그에 따라 속성 추가 마법사의 옵션을 수정합니다.<br /><br /> - [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용하여 만든 프로젝트의 dispinterface의 경우, 속성 추가 마법사를 호출하면 MFC 관련 옵션이 제공됩니다.<br />- MFC ActiveX 컨트롤 인터페이스의 경우, 속성 추가 마법사는 제공된 대로 사용하거나 컨트롤을 사용자 지정할 수 있는 스톡 메서드 및 속성 목록을 제공합니다.<br />- 다른 모든 인터페이스의 경우, 속성 추가 마법사는 대부분의 상황에서 유용한 옵션을 제공합니다.|  
|[메서드 추가 마법사](../ide/add-method-wizard.md)|ATL을 지원하는 ATL 또는 MFC 프로젝트. 메서드를 추가할 인터페이스를 마우스 오른쪽 단추로 클릭합니다.<br /><br /> Visual C++ 프로젝트 형식을 검색하고 그에 따라 메서드 추가 마법사의 옵션을 수정합니다.<br /><br /> - [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용하여 만든 프로젝트의 dispinterface의 경우, 메서드 추가 마법사를 호출하면 MFC 관련 옵션이 제공됩니다.<br />- MFC ActiveX 컨트롤 인터페이스의 경우, 메서드 추가 마법사는 제공된 대로 사용하거나 컨트롤을 사용자 지정할 수 있는 스톡 메서드 및 속성 목록을 제공합니다.<br />- 다른 모든 인터페이스의 경우, **메서드 추가** 마법사는 대부분의 상황에서 유용한 옵션을 제공합니다.|  
  
 또한 클래스 뷰에서 개체의 컨트롤 클래스를 마우스 오른쪽 단추로 클릭하고, [인터페이스 구현](../ide/implement-interface-wizard.md)을 클릭하여 COM 컨트롤에 새 인터페이스를 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일 작업](../windows/working-with-resource-files.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++ 프로젝트 형식](../ide/visual-cpp-project-types.md)