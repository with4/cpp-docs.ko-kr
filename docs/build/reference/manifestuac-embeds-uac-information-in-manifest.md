---
title: "/MANIFESTUAC(매니페스트에 UAC 정보 포함) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UACUIAccess"
  - "VC.Project.VCLinkerTool.UACExecutionLevel"
  - "VC.Project.VCLinkerTool.EnableUAC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTUAC 링커 옵션"
  - "MANIFESTUAC 링커 옵션"
  - "-MANIFESTUAC 링커 옵션"
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTUAC(매니페스트에 UAC 정보 포함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램 매니페스트에 UAC\(사용자 계정 컨트롤\) 정보를 포함할지 여부를 지정합니다.  
  
## 구문  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### 매개 변수  
 `fragment`  
 `level` 및 `uiAccess` 값이 포함된 문자열입니다.  자세한 내용은 이 항목의 뒤에 나오는 설명 부분을 참조하십시오.  
  
 `_level`  
 *asInvoker*, *highestAvailable* 또는 *requireAdministrator* 중 하나입니다.  기본값은 asInvoker입니다.  자세한 내용은 이 항목의 뒤에 나오는 설명 부분을 참조하십시오.  
  
 `_uiAccess`  
 `true` 만약 응용 프로그램이 사용자 인터페이스 보호 수준을 지나치길 원하거나 데스크탑의 높은 허용 인풋 창을 원할 경우; 다른 경우, `false`.  기본값은 `false`입니다.  사용자 인터페이스 내게 필요한 옵션 지원 응용 프로그램에 대해서만 `true`로 설정합니다.  
  
## 설명  
 명령줄에 여러 \/MANIFESTUAC 옵션을 지정하면 입력한 마지막 옵션의 우선 순위가 가장 높습니다.  
  
 \/MANIFESTUAC:level의 선택 항목은 다음과 같습니다.  
  
-   `asInvoker`: 응용 프로그램을 시작한 프로세스와 동일한 권한으로 응용 프로그램이 실행됩니다.  **관리자 권한으로 실행**을 선택하면 응용 프로그램의 권한 수준을 높일 수 있습니다.  
  
-   highestAvailable: 최대한 높은 권한 수준으로 응용 프로그램이 실행됩니다.  응용 프로그램을 시작하는 사용자가 관리자 그룹의 멤버이면 이 옵션은 requireAdministrator와 같습니다.  사용 가능한 가장 높은 권한 수준이 응용 프로그램을 여는 프로세스의 수준보다 높으면 자격 증명을 입력하라는 메시지가 표시됩니다.  
  
-   requireAdministrator: 응용 프로그램이 관리자 권한으로 실행됩니다.  응용 프로그램을 시작하는 사용자는 관리자 그룹의 멤버이어야 합니다.  응용 프로그램을 여는 프로세스가 관리자 권한으로 실행되고 있지 않은 경우 자격 증명을 입력하라는 메시지가 표시됩니다.  
  
 \/MANIFESTUAC:fragment 옵션을 사용하여 1단계에서 수준 및 uiAccess 값을 지정할 수 있습니다.  fragment는 다음 형식이어야 합니다.  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **매니페스트 파일** 속성 페이지를 선택합니다.  
  
5.  **UAC\(사용자 계정 컨트롤\) 사용**, **UAC 실행 수준** 및 **UAC UI 보호 건너뛰기** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)