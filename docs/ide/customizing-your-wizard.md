---
title: "마법사 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 지정 마법사"
  - "사용자 지정 마법사, Visual C++ 프로젝트에서 만들기"
ms.assetid: a3ff1c81-3eef-41e7-a6bc-2f98e4bf423f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[사용자 지정 마법사](../ide/application-settings-custom-wizard.md)를 사용하여 만든 마법사를 사용자 지정할 경우 다음 작업을 고려해야 합니다.  
  
-   마법사가 작동하기 위해 필요한 사용자 지정 매개 변수를 .vsz 파일에 지정합니다.  자세한 내용은 [.vsz 파일\(프로젝트 컨트롤\)](../ide/dot-vsz-file-project-control.md) 및 [미리 정의된 사용자 지정 마법사 기호](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)를 참조하십시오.  
  
     마법사를 여러 언어로 지역화하려면 각 언어 매개 변수를 .vsz 파일에 추가합니다.  자세한 내용은 [여러 언어로 마법사 지역화](../ide/localizing-a-wizard-to-multiple-languages.md)를 참조하십시오.  
  
-   [템플릿 파일](../ide/template-files.md) 및 [Templates.inf](../ide/templates-inf-file.md) 파일을 사용자 지정하여 사용자의 선택에 대한 지시문을 지정합니다.  
  
-   [Default.js 파일](../ide/jscript-file.md)을 사용자 지정하여 마법사에 대한 특수 처리를 추가로 지정합니다.  사용자 함수를 직접 만들 수도 있고 [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)에 있는 함수를 사용할 수도 있습니다.  
  
-   HTML 사용자 인터페이스에 사용할 아이콘과 기타 이미지를 디자인합니다.  
  
-   HTML 사용자 인터페이스를 디자인합니다.  
  
-   HTML 기호 테이블에 기호를 추가하여 마법사에서 사용하는 단추, 컨트롤, 텍스트 상자 및 기타 요소를 일치시킵니다.  
  
     다음 예제는 사용자 지정 마법사에서 제공하는 HTML의 일부 코드입니다.  
  
    ```  
    <SYMBOL NAME="WIZARD_DIALOG_TITLE" TYPE=text VALUE="MyCustomWiz">  
          </SYMBOL>  
    <SYMBOL NAME="SAMPLE_CHECKBOX" TYPE=checkbox VALUE=true>  
          </SYMBOL>  
    ```  
  
     이 MyCustomWiz 마법사에는 기본적으로 선택되는 확인란이 있습니다.  
  
-   HTML 파일에서 `<SCRIPT LANGUAGE="JSCRIPT">`라고 표시된 섹션에 JScript 함수 호출을 추가하고 Visual Studio 개체 모델에 액세스하여 마법사의 동작을 사용자 지정합니다.  다음과 같이 `window.external`을 사용하여 이 함수를 호출해야 합니다.  
  
    ```  
    window.external.AddSymbol("MAIN_FRAME_DEFAULT_STYLES", true);  
    window.external.AddSymbol("MAIN_FRAME_STYLE_FLAGS", "");  
    ```  
  
    > [!NOTE]
    >  [Automation and Extensibility for Visual Studio](../Topic/Automation%20and%20Extensibility%20for%20Visual%20Studio.md), [Visual C\+\+ 코드 모델](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b), [프로젝트 모델](http://msdn.microsoft.com/ko-kr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f) 및 [마법사 모델](http://msdn.microsoft.com/ko-kr/159395ac-33c7-47bf-ad42-4e1435ddc758)을 통해 노출되는 메서드, 속성 및 이벤트를 사용하면 JScript 파일과 .htm 파일 모두에서 마법사 프로젝트를 만들 때부터 빌드할 때까지의 모든 단계를 프로그래밍 방식으로 관리할 수 있습니다.  
  
-   필요하면 셸에서 .vsz 파일과 다른 모든 템플릿에 대한 정보를 인식하도록 [.vsdir 파일](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)을 사용자 지정합니다.  예를 들어, 아이콘 리소스 ID, 플래그, 지역화된 이름 등을 지정합니다.  
  
-   마법사를 지역화해야 하는 모든 언어로 .htm 파일과 템플릿 파일을 만듭니다.  만든 파일을 필요한 프로젝트 디렉터리에 추가합니다.  
  
-   마법사에 대한 [상황에 맞는 도움말 표시](../ide/providing-context-sensitive-help.md)합니다.  
  
## 참고 항목  
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인 단계](../ide/steps-to-designing-a-wizard.md)   
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [상황에 맞는 도움말 표시](../ide/providing-context-sensitive-help.md)   
 [마법사에서 오류 처리](../ide/handling-errors-in-wizards.md)