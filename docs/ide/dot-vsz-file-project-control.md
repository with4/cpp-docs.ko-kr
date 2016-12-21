---
title: ".Vsz 파일(프로젝트 컨트롤) | Microsoft Docs"
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
  - ".vsz 파일"
  - "사용자 지정 마법사, .vsz 파일"
  - "사용자 지정 마법사, 프로젝트 제어 파일"
  - "파일[C++], 사용자 지정 마법사로 만들기"
  - "vsz 파일"
ms.assetid: b8678fee-6795-46d1-9338-48b22d5e9207
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# .Vsz 파일(프로젝트 컨트롤)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 마법사는 .vsz 파일에서 시작됩니다.  .vsz 파일은 호출할 마법사와 마법사에 전달할 정보를 결정하는 텍스트 파일입니다.  이 파일에는 두 줄의 헤더가 있습니다. 헤더 뒤에는 마법사에 전달할 여러 가지 선택적 매개 변수가 나옵니다.  선택적 매개 변수 목록은 [미리 정의된 사용자 지정 마법사 기호](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)를 참조하십시오.  
  
 다음은 .vsz 파일의 헤더에 대한 샘플입니다.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine.10.0  
Param="WIZARD_NAME = My AppWizard"  
```  
  
-   헤더의 첫 번째 줄은 템플릿 파일 형식의 버전 번호를 지정합니다.  이 번호를 `6.0`, `7.0` 또는 `7.1`로 지정할 수 있습니다.  다른 번호는 사용할 수 없습니다. 다른 번호를 사용하면 "잘못된 형식입니다."라는 오류가 발생합니다.  
  
-   두 번째 줄은 **Wizard** 변수를 Visual Studio에서 만든 마법사의 ProgID로 설정합니다.  ProgID는 `VsWizard.VsWizardEngine.10.0`과 같이 CLSID를 문자열로 표현한 것입니다.  
  
     마법사에 사용자 인터페이스가 있으면 ProgID에서 마법사가 <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>를 구현하도록 지정합니다.  기본적으로 이 인터페이스의 메서드는 프로젝트의 [.htm 파일](../ide/html-files.md)에서 사용됩니다.  .htm 파일에 구현된 이 인터페이스의 메서드를 사용하여 마법사의 동작을 변경할 수 있습니다.  자세한 내용은 <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>의 coclass인 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>을 참조하십시오.  
  
-   이 두 줄 뒤에는 .vsz 파일에서 추가 사용자 지정 매개 변수를 마법사에 전달할 수 있도록 해주는 선택적 매개 변수 목록이 있습니다.  각 값은 variant 형식 배열의 문자열 요소로서 마법사 컨트롤의 <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> 메서드에 전달됩니다.  기본적으로, 사용자 인터페이스가 있는 마법사는 다음과 같은 기본 매개 변수를 만듭니다.  
  
    ```  
    Param="START_PATH = <path to the wizard>"  
    Param="HTML_PATH = <path to the wizard's HTML file>"  
    Param="TEMPLATES_PATH = <path to the wizard's template file>"  
    Param="SCRIPT_PATH = <path to the wizard's script files>"  
    Param="IMAGES_PATH = <path to the wizard's images>"  
    ```  
  
     마법사에 사용자 인터페이스가 없으면 `IMAGES_PATH` 매개 변수가 없고 대신 다음 매개 변수가 포함됩니다.  
  
    ```  
    Param="WIZARD_UI = FALSE"  
    Param="SOURCE_FILTER = txt"  
    ```  
  
-   .vsz 파일에 다음 매개 변수가 포함될 수도 있습니다. 이 매개 변수는 [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) 파일에 있는 함수를 지정합니다.  
  
    ```  
    Param="PREPROCESS_FUNCTION = CanAddATLClass"  
    Param="PREPROCESS_FUNCTION = CanAddMFCClass"  
    Param="PREPROCESS_FUNCTION = CanAddClass"  
    ```  
  
 [CanAddATLClass](../ide/canaddatlclass.md), [CanAddMFCClass](../ide/canaddmfcclass.md) 및 [CanAddClass](../ide/canaddclass.md) 함수는 [Visual C\+\+ Code Model](http://msdn.microsoft.com/ko-kr/dd6452c2-1054-44a1-b0eb-639a94a1216b)을 사용할 수 있는지 확인하기 위해 마법사에서 호출됩니다.  함수 하나라도 **false**를 반환하면 마법사가 실행되지 않습니다.  
  
 .vsz 파일이 vcprojects 디렉터리에 있으면 Visual Studio의 **새 프로젝트** 대화 상자에서 템플릿 창에 마법사를 추가할 수 있습니다.  기본적으로 사용자 지정 마법사는 이 디렉터리에 .vsz 파일을 만듭니다.  
  
> [!NOTE]
>  마법사 파일과 디렉터리를 삭제할 경우에는 vcprojects 디렉터리에서 프로젝트의 .vsz 파일, .vsdir 파일 및 .ico 파일도 삭제해야 합니다.  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [Visual C\+\+ Wizard Model](http://msdn.microsoft.com/ko-kr/159395ac-33c7-47bf-ad42-4e1435ddc758)   
 [Adding Wizards to the Add Item and New Project Dialog Boxes by Using .Vsdir Files](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)