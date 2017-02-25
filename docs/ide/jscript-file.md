---
title: "JScript 파일 | Microsoft Docs"
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
  - "AddConfig 메서드"
  - "AddFilesToCustomProj 메서드"
  - "AddFilters 메서드"
  - "Common.js 파일"
  - "CreateCustomInfFile 메서드"
  - "CreateCustomProject 메서드"
  - "사용자 지정 마법사, 마법사 개체 모델 액세스"
  - "사용자 지정 마법사, JScript 파일"
  - "디버깅[JScript], 스크립트 디버깅 사용"
  - "디버깅[JScript], JScript 파일"
  - "스크립트 디버깅"
  - "스크립트 디버깅, 스크립트 디버깅 사용"
  - "Default.js 파일"
  - "DelFile 메서드"
  - "파일[C++], 사용자 지정 마법사로 만들기"
  - "GetTargetName 메서드"
  - "JScript 파일"
  - "OnFinish 메서드"
  - "PchSettings 메서드"
ms.assetid: 7841a09e-2dd2-4f1a-a13a-39ac53f24315
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# JScript 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[사용자 지정 마법사](../ide/custom-wizard.md)는 스크립트 엔진에 액세스하여 프로젝트마다 Default.js라는 JScript 파일을 만듭니다.  이 마법사에서 만드는 파일에는 [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)도 포함됩니다.  이 파일에는 마법사를 사용자 지정하기 위해 Visual Studio 및 Visual C\+\+ 개체 모델에 액세스하는 JScript 함수가 포함됩니다.  이 모델의 목록은 [마법사 디자인](../ide/designing-a-wizard.md)을 참조하십시오. 사용자 고유의 함수를 마법사 프로젝트의 Default.js 파일에 추가할 수 있습니다.  JScript 파일에서 마법사 개체 모델이나 환경 모델의 속성과 메서드에 액세스하려면 개체 모델 항목 앞에 "wizard." 및 "dte."를 각각 추가하십시오.  
  
 예를 들면 다음과 같습니다.  
  
```  
function CreateCustomProject(strProjectName, strProjectPath)  
{  
   try  
   {  
      var strProjTemplatePath = wizard.FindSymbol('PROJECT_TEMPLATE_PATH');  
var strProjTemplate = '';  
      strProjTemplate = strProjTemplatePath + '\\default.vcproj';  
  
      var Solution = dte.Solution;  
      var strSolutionName = "";  
      if (wizard.FindSymbol("CLOSE_SOLUTION"))  
...  
```  
  
 [사용자 지정 마법사](../ide/custom-wizard.md)에서 **마침**을 클릭하면 마법사가 솔루션 탐색기의 스크립트 파일 폴더에 있는 Default.js 파일을 로드합니다.  이 JScript 파일은 프로젝트를 만들고 템플릿을 렌더링한 다음, 사용자가 마법사에서 **마침**을 클릭할 때 솔루션에 추가합니다.  
  
 기본적으로 프로젝트의 Default.js 파일에는 다음과 같은 함수가 포함됩니다.  
  
|함수 이름|설명|  
|-----------|--------|  
|**AddConfig**|프로젝트의 구성을 추가합니다.  컴파일러 및 링커 설정을 추가할 수 있습니다.|  
|**AddFilesToCustomProj**|**마침**을 클릭하면 지정된 파일이 프로젝트에 추가됩니다.|  
|**AddFilters**|**마침**을 클릭하면 지정된 소스 필터가 프로젝트에 추가됩니다.|  
|**CreateCustomProject**|**마침**을 클릭하면 지정된 위치에 프로젝트가 만들어집니다.|  
|**CreateCustomInfFile**|프로젝트의 [Templates.inf 파일](../ide/templates-inf-file.md)을 만듭니다.|  
|**DelFile**|지정한 파일을 삭제합니다.|  
|**GetTargetName**|지정된 파일의 이름을 가져옵니다.|  
|**OnFinish**|**마침**을 클릭할 때 마법사에 의해 호출되어 프로젝트를 만들고, 파일과 필터를 추가하고, 템플릿을 렌더링하고, 구성을 설정합니다.|  
|**PchSettings**|미리 컴파일된 헤더 설정을 지정합니다.  자세한 내용은 Common.js 참조에서 [SetCommonPchSettings](../ide/setcommonpchsettings.md)를 참조하십시오.|  
  
 각 마법사에는 고유의 Default.js 파일이 있는데, 이 파일에는 파일을 사용자 지정해야 하는 위치를 나타낸 TODO 주석이 포함되어 있습니다.  
  
 Visual C\+\+에는 마법사 프로젝트에 포함되고 모든 마법사에서 공유하는 [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) 파일도 들어 있습니다.  Common.js 파일에서 함수를 사용할 수 있습니다.  
  
> [!NOTE]
>  Common.js 파일에는 각 함수와 함수의 매개 변수에 대한 설명이 있습니다.  자세한 내용은 Common.js 파일의 주석을 참조하십시오.  
  
 마법사 프로젝트 사이에 공유하려는 함수는 Common.js 파일에 추가할 수 있습니다.  사용자 고유의 Common.js 버전을 만들어 공용 경로에 저장한 다음, [.vsz 파일](../ide/dot-vsz-file-project-control.md)에서 SCRIPT\_COMMON\_PATH를 이 경로로 설정하십시오.  
  
> [!NOTE]
>  Visual C\+\+에 포함된 마법사는 Common.js에 있는 JScript 함수를 사용합니다.  이 함수를 변경하면 Visual C\+\+ 마법사가 비정상적으로 작동할 수 있습니다.  
  
 JScript에 대한 자세한 내용은 [Writing, Compiling, and Debugging JScript Code](http://msdn.microsoft.com/ko-kr/13e57e7d-4867-4555-b9e4-fc24aa75e628)을 참조하십시오.  
  
## 스크립트 디버깅  
 마법사 html 파일의 스크립트를 디버깅하려면 스크립트 디버깅을 사용해야 합니다.  
  
#### 스크립트 디버깅을 사용하려면  
  
1.  Internet Explorer에서 **도구** 메뉴를 클릭하고 **인터넷 옵션**을 선택합니다.  
  
2.  **고급** 탭을 클릭합니다.  
  
3.  **탐색** 범주에서 **스크립트 디버깅 사용 안 함** 확인란을 선택 취소합니다.  
  
 또한 이렇게 하면 마법사의 마침 단추를 클릭할 때 **실행 중인 문서** 창에 common.js 및 default.js가 표시됩니다.  
  
## 참고 항목  
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)