---
title: "마법사 .Vsz 파일의 사용자 지정 매개 변수 | Microsoft Docs"
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
  - "ABSOLUTE_PATH 매크로"
  - "사용자 지정 마법사, .vsz 파일"
  - "HTML_FILTER 매크로"
  - "HTML_PATH 매크로"
  - "IMAGE_FILTER 매크로"
  - "IMAGES_PATH 매크로"
  - "MISC_FILTER 매크로"
  - "PRODUCT 매크로"
  - "PRODUCT_INSTALLATION_DIR 매크로"
  - "PROJECT_TEMPLATE_NAME 매크로"
  - "PROJECT_TEMPLATE_PATH 매크로"
  - "RELATIVE_PATH 매크로"
  - "SCRIPT_COMMON_PATH 매크로"
  - "SCRIPT_FILTER 매크로"
  - "SCRIPT_PATH 매크로"
  - "START_PATH 매크로"
  - "TEMPLATE_FILTER 매크로"
  - "TEMPLATES_PATH 매크로"
  - "WIZARD_NAME 매크로"
  - "WIZARD_UI 매크로"
ms.assetid: 560dd5c0-7cff-4974-b856-5ca25b0669b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 .Vsz 파일의 사용자 지정 매개 변수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.vsz 파일의 처음 두 줄에서는 마법사 버전 및 공동으로 만드는 마법사의 ProgID 또는 CLSID를 식별합니다.  .vsz 파일에는 HTML 기호 섹션에서 제공되는 기호와 함께 기호 테이블에 추가되는 선택적 컨텍스트 매개 변수와 사용자 지정 매개 변수도 포함될 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> 메서드는 .vsz 파일에 정의된 컨텍스트 및 사용자 지정 매개 변수의 배열을 매개 변수로 사용하는 마법사를 표시합니다.  
  
 다음과 같은 공용 기호가 [.vsz 파일](../ide/dot-vsz-file-project-control.md) 또는 .htm 파일에 사용자 지정 매개 변수로 지정되어, 마법사 HTML, 스크립트 또는 템플릿 파일에 사용될 수 있습니다.  
  
## 예제  
 다음 .vsz 파일 엔트리에 나타나는 것처럼, MyProjWiz 마법사에는 사용자 인터페이스가 포함됩니다.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine  
Param="WIZARD_NAME = MyProjWiz"  
Param="WIZARD_UI = TRUE"  
```  
  
### 마법사 .vsz 파일에서 사용자 지정 매개 변수로 사용되는 기호  
  
|기호|정의|  
|--------|--------|  
|ABSOLUTE\_PATH|마법사 파일의 위치를 지정합니다.|  
|HTML\_FILTER|.vsz 파일에 지정됩니다.  **솔루션 탐색기**의 HTML 파일 폴더에 있는 파일 형식을 지정합니다.  일반적으로 "htm"으로 지정됩니다.|  
|HTML\_PATH|.vsz 파일에 지정됩니다.  마법사의 [HTML 파일](../ide/html-files.md) 위치를 지정합니다.  기본적으로 이 위치는 START\_PATH\\HTML\\*LANGUAGE*입니다. 여기서 *LANGUAGE*는 시스템 레지스트리에 지정된 로캘입니다. **Note:**  \<LangID\>를 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage에서 10진수 값으로 설정하여 다른 언어를 지정할 수 있습니다.  자세한 내용은 [여러 언어로 마법사 지역화](../ide/localizing-a-wizard-to-multiple-languages.md)를 참조하십시오.  십진수 언어 값 목록은 [다른 언어에 대한 마법사 지원](../ide/wizard-support-for-other-languages.md)을 참조하십시오.|  
|IMAGE\_FILTER|.vsz 파일에 지정됩니다.  솔루션 탐색기의 이미지 파일 폴더에 있는 파일 형식을 지정합니다.  일반적으로 "bmp;gif"로 지정됩니다.|  
|IMAGES\_PATH|.vsz 파일에 지정됩니다.  html 파일에 사용되는 이미지 파일의 위치를 지정합니다.  기본 위치는 START\_PATH\\Images입니다.|  
|MISC\_FILTER|.vsz 파일에 지정됩니다.  솔루션 탐색기의 Misc 폴더에 있는 파일 형식을 지정합니다.  일반적으로 "vsz;vsdir;ico;vcproj;csproj;css;inf"로 지정됩니다.|  
|PRODUCT|기본적으로 Visual C\+\+로 설정하지만, 이 값을 Visual Basic으로 설정하여 Visual Basic 마법사를 만들 수 있으며 그 외의 경우도 가능합니다.|  
|PRODUCT\_INSTALLATION\_DIR|레지스트리의 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\\<Product\>\\ ProductDir에 표시되는 디렉터리입니다.|  
|PROJECT\_TEMPLATE\_NAME|.vsz 파일에 지정됩니다.  마법사에서 프로젝트를 만드는 데 사용하는 프로젝트 템플릿입니다.  일반적으로 "txt"로 지정됩니다.|  
|PROJECT\_TEMPLATE\_PATH|프로젝트의 [템플릿 파일](../ide/template-files.md)이 있는 디렉터리입니다.  Visual C\+\+인 경우에는 기본값이 PRODUCT\_INSTALLATION\_DIR\\VCWizards입니다.|  
|RELATIVE\_PATH|ABSOLUTE\_PATH가 없으면 RELATIVE\_PATH가 사용됩니다.  이것은 PRODUCT\_INSTALLATION\_DIR을 기준으로 한 상대 경로입니다.  Visual C\+\+에서는 RELATIVE\_PATH가 PRODUCT\_INSTALLATION\_DIR\\VCWizards입니다.|  
|SCRIPT\_COMMON\_PATH|공용 스크립트 파일이 있는, PRODUCT\_INSTALLATION\_DIR를 기준으로 한 상대 경로 디렉터리의 이름입니다.  예를 들어, Visual C\+\+에서는 이 이름이 VCWizards입니다.|  
|SCRIPT\_FILTER|.vsz 파일에 지정됩니다.  솔루션 탐색기의 스크립트 파일 폴더에 있는 파일 형식을 지정합니다.  일반적으로 "js"\(JScript\) 또는 "vbs"\(VBScript\)로 지정됩니다.|  
|SCRIPT\_PATH|마법사의 [JScript 파일](../ide/jscript-file.md) 위치를 지정합니다.  기본적으로 이 위치는 START\_PATH\\Scripts입니다.|  
|START\_PATH|.vsz 파일에 지정됩니다.  이 경로는 사용자가 설정하지 않고, RELATIVE\_PATH 또는 ABSOLUTE\_PATH를 식별하는 데 내부적으로 사용됩니다.  이 값에 마법사 이름\(WIZARD\_NAME\)이 추가됩니다.|  
|TEMPLATE\_FILTER|.vsz 파일에 지정됩니다.  솔루션 탐색기에서 Template Files 폴더에 들어가는 파일 형식을 지정합니다.  일반적으로 "txt"로 지정됩니다.|  
|TEMPLATES\_PATH|.vsz 파일에 지정됩니다.  마법사의 템플릿 파일 위치를 지정합니다.  기본적으로 이 위치는 START\_PATH\\Templates\\\<LangID\>입니다. **Note:**  LangID에 대한 자세한 내용은 HTML\_PATH를 참조하십시오.|  
|WIZARD\_NAME|마법사 이름을 지정합니다.  .vsz 파일에 있으며 나머지 기호에 의해 사용됩니다.|  
|WIZARD\_UI|.vsz 파일에 지정됩니다.  마법사의 사용자 인터페이스 포함 여부를 나타내는 부울 값입니다.  사용자 인터페이스를 포함할 경우에는 **TRUE**를 지정하고 사용자 인터페이스를 포함하지 않을 경우에는 **FALSE**를 지정합니다.|  
  
## 참고 항목  
 <xref:EnvDTE.IDTWizard.Execute%2A>   
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)