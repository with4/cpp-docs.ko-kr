---
title: "MFC DLL 프로젝트 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [C++], creating projects
- DLLs [C++], MFC
- projects [C++], creating
- DLLs [C++], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c403d1351c43e043fd3048d342dafcf069951446
ms.lasthandoff: 02/24/2017

---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL 프로젝트 만들기
MFC DLL은 여러 응용 프로그램에서 동시에 사용할 수 있는 함수의 공유 라이브러리로 사용 되는 이진 파일. MFC DLL 프로젝트를 만드는 가장 쉬운 방법은 MFC DLL 마법사를 사용 하 여 됩니다.  
  
> [!NOTE]
>  IDE의 기능이의 모양을 활성 설정이 나 버전에 따라 달라질 수 다를 수 있습니다 도움말에서 설명 하는 것입니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL 마법사를 사용 하 여 MFC DLL 프로젝트를 만들려면  
  
1.  도움말 항목의 지침에 따라 [Visual c + + 응용 프로그램 마법사로 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)합니다.  
  
 **참고** 에 **새 프로젝트** 대화 상자는 `MFC DLL` MFC DLL 마법사를 열려면 템플릿 창에서 아이콘입니다.  
  
1.  사용 하 여 응용 프로그램 설정을 정의 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-dll-wizard.md) 의 페이지는 [MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)합니다.  
  
    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.  
  
2.  클릭 **마침** 는 마법사를 닫고에서 새 프로젝트를 열고 **솔루션 탐색기**합니다.  
  
 프로젝트가 만들어지면 솔루션 탐색기에서 만든 파일을 볼 수 있습니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대 한 자세한 내용은 참조 [Visual c + + 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual c + + 프로젝트 형식](http://msdn.microsoft.com/library/912b4ba2-7719-43d5-b087-db33e3f9329a)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [응용 프로그램 배포](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


