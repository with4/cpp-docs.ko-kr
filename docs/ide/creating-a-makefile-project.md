---
title: "메이크파일 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.makefile.project
dev_langs: C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e86bedbf83cd417cfc41317e5887304cda7ee76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-makefile-project"></a>메이크파일 프로젝트 만들기
메이크파일을 사용하여 명령줄에서 프로젝트를 빌드하면 Visual Studio 개발 환경에서 프로젝트를 인식하지 못합니다. 열고 사용 하 여 프로젝트를 빌드하려고 [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], Visual Studio Professional 또는 Visual Studio Express for Windows Desktop을 먼저 만드는 빈 프로젝트 메이크파일 프로젝트 템플릿을 선택 하 여 합니다. 그런 다음 이 프로젝트를 사용하여 Visual Studio 개발 환경에서 프로젝트를 빌드할 수 있습니다.  
  
 프로젝트는 솔루션 탐색기에 파일을 표시하지 않습니다. 프로젝트에서는 빌드 설정을 지정하고, 설정 내용은 프로젝트의 속성 페이지에 반영됩니다.  
  
 프로젝트에서 지정하는 출력 파일은 빌드 스크립트가 생성하는 이름에는 영향을 미치지 않으며 의도만 선언합니다.  
  
### <a name="to-create-a-makefile-project"></a>메이크파일 프로젝트를 만들려면  
  
1.  도움말 항목의 지침에 따라 [Visual c + + 응용 프로그램 마법사로 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **메이크파일 프로젝트** 마법사를 열려면 템플릿 창에서.  
  
3.  에 [응용 프로그램 설정](../ide/application-settings-makefile-project-wizard.md) 페이지, 명령을 제공할 출력, 정리 및 다시 빌드 정보입니다.  
  
4.  클릭 **마침** 는 마법사를 닫고에서 새로 만든된 프로젝트를 열 **솔루션 탐색기**합니다.  
  
 속성 페이지에서 프로젝트의 속성을 보고 편집할 수 있습니다. 참조 [Visual c + + 프로젝트 속성 설정](../ide/working-with-project-properties.md) 속성 페이지를 표시 하는 방법에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일 프로젝트 마법사](../ide/makefile-project-wizard.md)   
 [메이크파일의 특수 문자](../build/special-characters-in-a-makefile.md)   
 [메이크파일의 내용](../build/contents-of-a-makefile.md)