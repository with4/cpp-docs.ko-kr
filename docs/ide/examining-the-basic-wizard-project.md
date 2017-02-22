---
title: "기본 마법사 프로젝트 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 지정 마법사, 생성된 파일"
  - "사용자 지정 마법사, 마법사 프로젝트"
ms.assetid: c6423e3c-ddb0-43e0-b8e5-9e3a98a7908c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 기본 마법사 프로젝트 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[사용자 지정 마법사](../ide/creating-a-custom-wizard.md)를 사용하여 기본 프로젝트를 만들었으면 마법사에서 만든 파일을 검사합니다.  
  
1.  **솔루션 탐색기**에서 프로젝트를 확장하고 마법사에서 프로젝트에 사용하기 위해 만든 [파일](../ide/files-created-for-your-wizard.md)을 검사합니다.  
  
2.  Default.js 파일을 두 번 클릭하여 코드 편집기에서 프로젝트의 [JScript 파일](../ide/jscript-file.md)을 엽니다.  이 파일에는 사용자가 마법사에서 **마침**을 클릭할 때 프로젝트를 만드는 JScript 함수가 있습니다.  이 파일에서 함수와 TODO 주석을 확인합니다.  
  
3.  프로젝트에 사용자 인터페이스가 있으면 [HTML 파일](../ide/html-files.md)이라고 표시된 폴더를 열고 사용자 지정 마법사의 [응용 프로그램 설정](../ide/application-settings-custom-wizard.md) 페이지에서 지정한 .htm 파일이 모두 있는지 확인합니다.  Default.htm 파일을 두 번 클릭하여 [HTML 디자이너](../Topic/HTML%20Designer.md)에서 프로젝트의 주 HTML 페이지를 엽니다.  HTML 파일은 [Design View](../Topic/Design%20View1.md)에서 볼 수도 있고 HTML 뷰에서 [HTML 태그](http://msdn.microsoft.com/ko-kr/7bb90672-b36a-4cf9-9bbc-677c9b956318)로 볼 수도 있습니다.  HTML 태그 뷰로 전환하여 HTML 태그를 확인합니다.  HTML 뷰 편집 창 오른쪽 위에서 **이벤트** 드롭다운 목록 옆에 있는 **스크립트 전용 뷰** 단추를 클릭하고 .htm 파일에서 JScript를 검사합니다.  기본적으로 이 파일에는 마법사를 초기화하고 로드하는 JScript 함수가 포함되어 있으며, 이 파일에서 **IVCWizCtrlUI** 인터페이스의 기본 동작을 제공합니다.  자세한 내용은 coclass <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl> 개체를 참조하십시오.  
  
4.  마법사 프로젝트를 저장하고 닫습니다.  
  
5.  Visual Studio **새 프로젝트** 대화 상자를 열고 마법사 아이콘을 찾습니다.  아이콘을 두 번 클릭하여 마법사를 표시합니다.  사용자 지정 마법사에서 만든 기본 마법사 페이지를 검사할 수 있습니다.  첫 번째 페이지에는 몇 가지 예제 HTML 컨트롤과 표준 **마침**, **취소** 및 **도움말** 단추가 있습니다.  
  
6.  마법사에서 **마침**을 클릭하여 새 프로젝트를 빌드합니다.  기본적으로 마법사는 ReadMe.txt 및 Sample.txt라는 두 개의 텍스트 파일을 만듭니다.  이 파일에는 마법사에서 만든 프로젝트에 대한 설명이 있습니다.  프로젝트를 닫고 마법사 프로젝트를 다시 엽니다.  
  
7.  마법사를 실행할 때 Visual Studio 환경과 Visual C\+\+ 마법사 엔진에서 프로젝트를 만드는 방법에 대한 자세한 내용은 [마법사의 메커니즘 검사](../ide/examining-the-mechanics-of-a-wizard.md)를 참조하십시오.  
  
 이제 [마법사 사용자 지정](../ide/customizing-your-wizard.md)을 시작할 준비가 되었습니다.  
  
## 참고 항목  
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인 단계](../ide/steps-to-designing-a-wizard.md)   
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [상황에 맞는 도움말 표시](../ide/providing-context-sensitive-help.md)   
 [마법사 사용자 지정](../ide/customizing-your-wizard.md)