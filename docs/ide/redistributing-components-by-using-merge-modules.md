---
title: "병합 모듈을 사용하여 구성 요소 재배포 | Microsoft Docs"
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
  - "병합 모듈, using"
  - "응용 프로그램 재배포, 병합 모듈 사용"
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# 병합 모듈을 사용하여 구성 요소 재배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에는 응용 프로그램으로 재배포할 권한이 있는 각 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 구성 요소에 대한 [병합 모듈](http://msdn.microsoft.com/library/aa367434)이 포함됩니다.  병합 모듈이 Windows Installer 설치 파일에서 컴파일되면 특정 플랫폼이 있는 컴퓨터에 특정 DLL을 배포할 수 있습니다.  설치 파일에서 병합 모듈을 응용 프로그램의 필수 구성 요소로 지정합니다.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]이 설치되면 병합 모듈이 \\Program Files\\Common Files\\Merge Modules\\에 설치됩니다. \(디버그가 아닌 버전의 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL만 재배포할 수 있습니다.\) 자세한 내용과 재배포 권한이 있는 병합 모듈 목록 링크는 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)를 참조하십시오.  
  
 병합 모듈을 사용하여 재배포 가능 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL을 %SYSTEMROOT%\\system32\\ 폴더에 설치할 수 있습니다. \([!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 자체가 이 기법을 사용합니다.\) 그러나 설치하는 사용자가 관리자 권한이 없는 경우 이 폴더에 설치되지 않습니다.  
  
 응용 프로그램을 제공할 필요가 없고 둘 이상의 DLL 버전에 대한 종속성이 없는 경우를 제외하고 병합 모듈을 사용하지 않는 것이 좋습니다.  동일한 DLL의 여러 버전에 대한 병합 모듈은 하나의 설치 관리자에 포함될 수 없고 병합 모듈은 응용 프로그램에 관계없이 DLL을 제공하기 어렵습니다.  대신에 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 재배포 가능 패키지를 설치하는 것이 좋습니다.  
  
## 참고 항목  
 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)