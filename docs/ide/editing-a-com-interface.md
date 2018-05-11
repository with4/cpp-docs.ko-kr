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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="editing-a-com-interface"></a>COM 인터페이스 편집
클래스 뷰 바로 가기 메뉴에서 명령을 사용 하면 Visual c + + 프로젝트에 새 메서드 및 COM 인터페이스에 대 한 속성을 정의할 수 있습니다. 도구 상자에서 ActiveX 컨트롤의 이벤트를 정의할 수 있습니다.  
  
 ATL 및 MFC 기반 COM 개체 클래스에 대 한 클래스 구현을 인터페이스를 편집 하는 동시에 편집할 수 있습니다.  
  
> [!NOTE]
>  외부에 정의 된 인터페이스에 대 한는 **클래스 추가** 대화 상자, Visual c + +.idl 파일에는 메서드 또는 속성을 추가 하 고 스텁을 인터페이스 수동으로 추가한 경우에 메서드를 구현 하는 클래스에 추가 합니다.  
  
 다음 세 가지 마법사 기존 인터페이스를 사용자 지정할 수 있습니다. 이러한 클래스 뷰에서 사용할 수 있습니다.  
  
|마법사|프로젝트 형식|  
|------------|------------------|  
|[속성 추가 마법사](../ide/names-add-property-wizard.md)|ATL 또는 MFC 프로젝트 ATL. 지원 속성을 추가 하려면 원하는 인터페이스를 마우스 오른쪽 단추로 클릭 합니다.<br /><br /> Visual c + + 프로젝트 형식에서 검색 하 고 속성 추가 마법사의 옵션을 적절 하 게 수정:<br /><br /> -를 사용 하 여 만든 프로젝트에서 dispinterface에 대 한는 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md), MFC에 관련 된 옵션을 제공 속성 추가 마법사를 호출 합니다.<br />-MFC ActiveX 컨트롤 인터페이스에 대 한 속성 추가 마법사 스톡 메서드 및 제공 된 그대로 사용 하거나 사용자 컨트롤에 사용자 지정할 수 있는 속성의 목록을 제공 합니다.<br />-다른 모든 인터페이스에 대 한 속성 추가 마법사는 대부분의 경우에 사용할 수 있는 옵션을 제공합니다.|  
|[메서드 추가 마법사](../ide/add-method-wizard.md)|ATL 또는 MFC 프로젝트 ATL. 지원 메서드를 추가 하려면 인터페이스를 마우스 오른쪽 단추로 클릭 합니다.<br /><br /> Visual c + + 프로젝트 형식에서 검색 하 고 메서드 추가 마법사의 옵션을 적절 하 게 수정:<br /><br /> -를 사용 하 여 만든 프로젝트에서 dispinterface에 대 한는 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md), MFC에 관련 된 옵션을 제공 메서드 추가 마법사를 호출 합니다.<br />-MFC ActiveX 컨트롤 인터페이스에 대 한 메서드 추가 마법사 스톡 메서드 및 제공 된 그대로 사용 하거나 사용자 컨트롤에 사용자 지정할 수 있는 속성의 목록을 제공 합니다.<br />-에 대해 다른 모든 인터페이스는 **메서드 추가** 대부분의 경우에 유용한 옵션을 제공 합니다.|  
  
 클래스 뷰에서 개체의 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 하 여 COM 컨트롤에 새 인터페이스를 구현할 수는 또한 [인터페이스 구현](../ide/implement-interface-wizard.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일 작업](../windows/working-with-resource-files.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++ 프로젝트 형식](../ide/visual-cpp-project-types.md)