---
title: "마법사용으로 만들어진 파일 | Microsoft Docs"
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
  - "사용자 지정 마법사, 파일 삭제"
  - "사용자 지정 마법사, 생성된 파일"
  - "파일[C++], 사용자 지정 마법사로 만들기"
  - "아이콘, 제거"
ms.assetid: 7f0e393c-395e-491b-add2-904cf8838e81
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 마법사용으로 만들어진 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사는 **새 프로젝트** 대화 상자의 **이름** 상자에서 지정하는 이름을 사용하여 몇 가지 파일과 클래스의 이름을 만듭니다.  
  
 [사용자 지정 마법사](../ide/custom-wizard.md)는 마법사에서 사용하기 위해 만든 파일에 주석을 추가합니다.  또한 사용자 지정 마법사는 새 응용 프로그램 디렉터리에 readme.txt 텍스트 파일을 만듭니다.  이 파일에는 사용자 지정 마법사에서 새로 만든 다른 파일의 내용과 용도에 대한 설명이 있습니다.  
  
 사용자 지정 마법사에서 만드는 파일에 대한 설명이 다음 표에 있습니다.  마법사를 만들기 위해 키 요소가 상호 작용하는 방법에 대한 자세한 내용은 [마법사 디자인](../ide/designing-a-wizard.md)을 참조하십시오.  
  
|파일|설명|  
|--------|--------|  
|[Project.vsz](../ide/dot-vsz-file-project-control.md)|이전의 .ini 형식과 유사한 텍스트 파일입니다.  이 파일에서는 마법사 엔진을 식별하고 컨텍스트 및 선택적인 [사용자 지정 매개 변수](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md)를 제공합니다.|  
|[Project.vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)|Visual Studio 셸을 사용하여 마법사를 찾아 **새 프로젝트** 대화 상자에 표시할 수 있도록 설정하는 텍스트 파일입니다.|  
|[HTML 파일\(옵션\)](../ide/html-files.md)|마법사에 HTML 인터페이스인 UI\(사용자 인터페이스\)를 포함할 수 있습니다.  UI가 없는 마법사에는 HTML 파일이 포함되지 않습니다.<br /><br /> 마법사에 UI가 있으면 마법사의 각 화면을 *페이지*라고 하고 각 페이지에서는 UI 기능을 지정합니다.<br /><br /> default.htm 파일은 마법사에 첫 번째 페이지를 정의합니다.  [사용자 지정 마법사, 응용 프로그램 설정](../ide/application-settings-custom-wizard.md)의 **페이지 수** 목록 상자를 사용하여 추가 페이지를 지정할 수 있습니다.  각각의 추가 페이지는 Page\_*page\-number*.htm 파일에서 정의되며 여기서 *page\-number*의 범위는 2부터 지정하는 페이지 수까지입니다.|  
|[스크립트 파일](../ide/jscript-file.md)|사용자 지정 마법사는 만든 각 마법사에 대해 JScript 파일인 default.js를 만듭니다.  이 파일에는 마법사를 사용자 지정하기 위해 Visual C\+\+ 마법사, 코드 및 환경 개체 모델에 액세스하는 JScript 함수가 포함되어 있습니다.  마법사의 default.js 파일에서 함수를 사용자 지정하고 추가할 수 있습니다.<br /><br /> 또한 마법사에는 공용으로 사용되는 JScript 함수가 있는 [common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) 파일이 포함됩니다. 이 파일은 Visual C\+\+에서 다른 프로젝트 형식을 만드는 데 사용하는 마법사를 포함하여 모든 마법사에서 공유됩니다.  자세한 내용은 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)을 참조하십시오.|  
|[템플릿](../ide/template-files.md)|마법사의 템플릿은 마법사 사용자의 선택에 따라 구문이 분석되어 기호 테이블에 삽입되는, 지시문이 포함된 텍스트 파일 모음입니다.  템플릿 텍스트 파일은 사용자의 입력에 따라 렌더링되어 마법사가 만든 프로젝트에 추가됩니다.  마법사 컨트롤의 기호 테이블에 직접 액세스하여 필요한 정보를 얻을 수 있습니다.|  
|[Templates.inf](../ide/templates-inf-file.md)|프로젝트와 연결된 모든 템플릿이 나열된 텍스트 파일입니다.|  
|Default.vcxproj|프로젝트 형식에 대한 정보가 포함된 .xml 파일입니다.|  
|Sample.txt|마법사 지시문 사용 방법이 표시된 템플릿 파일입니다.|  
|ReadMe.txt|사용자 지정 마법사에서 만드는 각 파일에 대한 요약 정보가 포함된 템플릿 파일입니다.|  
|이미지\(선택적 요소\)|아이콘, GIF, BMP 및 기타 HTML 지원 이미지 형식과 같은 이미지를 제공하여 마법사의 UI를 향상시킬 수 있습니다.  UI가 없는 마법사에는 이미지가 필요 없습니다.|  
|Styles.css\(선택적 요소\)|UI의 서식을 정의하는 파일입니다.  마법사에 사용자 인터페이스가 없으면 사용자 지정 마법사에서 .css 파일을 만들지 않습니다.|  
  
 마법사 파일과 디렉터리를 삭제할 경우에는 \\vc7\\vcprojects\\ 디렉터리에서 다음 파일도 삭제해야 합니다.  이 파일을 삭제하지 않으면 마법사 아이콘이 계속 **새 프로젝트** 대화 상자에 나타납니다.  
  
-   *projectname*.vsz  
  
-   *projectname*.ico  
  
-   *projectname*.vsdir  
  
## 참고 항목  
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [마법사 디자인](../ide/designing-a-wizard.md)   
 [공용 JScript 함수를 사용하여 C\+\+ 마법사 사용자 지정](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)