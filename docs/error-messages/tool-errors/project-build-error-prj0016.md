---
title: "프로젝트 빌드 오류 PRJ0016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0016"
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 프로젝트 빌드 오류 PRJ0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자의 보안 설정 때문에 프로세스를 만들 수 없습니다.이 설정은 빌드에 필요합니다.  
  
 프로세스를 사용하여 프로세스를 만들 수 있는 권한이 없는 사용자로 로그인했습니다.  이 사용자 계정에 대한 권한 수준을 변경하거나 계정 관리자에게 문의해야 합니다.  
  
 이 오류는 다음 레지스트리 키가 설정된 경우에도 발생할 수 있습니다.  
  
 \\\\HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun  
  
 이 오류를 해결하려면 RestrictRun 키를 삭제하십시오.  이 레지스트리 키가 필요할 경우에는 키의 항목 목록 끝에 **vcspawn.exe**를 추가하십시오.  
  
 이 오류의 또 다른 원인은 정책 설정에서 VCSpawn.exe가 이 사용자 계정에 대해 허용된 Windows 응용 프로그램으로 HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\RestrictRun 레지스트리 키 아래에 들어 있지 않기 때문입니다.  
  
 추가 정보를 보려면 다음을 참조하십시오.  
  
-   사용할 수 있는 기술 자료 문서 324153, [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [시스템 정책 설정 준수](http://msdn.microsoft.com/library/aa372139)의 "허용된 Windows 응용 프로그램만 실행" 단원