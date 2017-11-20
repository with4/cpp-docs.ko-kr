---
title: "MFC ActiveX 컨트롤 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.activex.project
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e01f0e0c1f24839f1d33184448559c1e8f48ceb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX 컨트롤 만들기
ActiveX 컨트롤 프로그램은 부모 응용 프로그램에 특정 종류의 기능을 제공 하도록 설계 모듈식 프로그램. 예를 들어 대화 상자에서 또는 웹 페이지에서 사용 하기 위해 도구 모음에서 사용 하기 위해 단추와 같은 컨트롤을 만들 수 있습니다.  
  
 MFC ActiveX 컨트롤을 만드는 가장 쉬운 방법은 사용 하는 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)합니다.  
  
### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사를 사용 하 여 MFC ActiveX 컨트롤을 만들려면  
  
1.  도움말 항목의 지침에 따라 [Visual c + + 응용 프로그램 마법사로 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **MFC ActiveX 컨트롤** MFC ActiveX 컨트롤 마법사를 열려면 템플릿 창에서 아이콘입니다.  
  
3.  정의 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md), 및 [설정을 제어](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사를 사용 하 여 합니다.  
  
    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.  
  
4.  클릭 **마침** 는 마법사를 닫고 개발 환경에서 새 프로젝트를 엽니다.  
  
 프로젝트를 만든 후에 생성 된 파일을 볼 수 있습니다 **솔루션 탐색기**합니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대 한 자세한 내용은 참조 [Visual c + + 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)합니다.  
  
 프로젝트를 만든 후 추가 하려면 코드 마법사를 사용할 수 있습니다 [함수](../../ide/add-member-function-wizard.md), [변수](../../ide/add-member-variable-wizard.md), [이벤트](../../ide/add-event-wizard.md), [속성](../../ide/names-add-property-wizard.md), 및 [메서드](../../ide/add-method-wizard.md)합니다. ActiveX 컨트롤을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [응용 프로그램 배포](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

