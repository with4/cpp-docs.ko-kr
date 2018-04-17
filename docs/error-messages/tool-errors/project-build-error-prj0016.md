---
title: 프로젝트 빌드 오류 PRJ0016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 056a033ce95926ca8bbf59e6bbc7b11656fcd015
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0016"></a>프로젝트 빌드 오류 PRJ0016
사용자의 보안 설정 때문에 프로세스 만들어지지 않도록 합니다. 이 설정은 빌드에 필요 합니다.  
  
 프로세스를 사용 하는 프로세스를 만들 권한이 있는 사용자로 로그인 합니다. 이 사용자 계정에 대 한 사용 권한 수준을 변경 하거나 계정 관리자에 게 문의 해야 합니다.  
  
 이 오류는 다음 레지스트리 키 설정 된 경우에 발생할 수 있습니다.  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 이 오류를 해결 하려면 RestrictRun 키를 삭제 합니다. 이 레지스트리 키가 필요한 경우 추가 **vcspawn.exe** 는 키의 항목 목록에 있습니다.  
  
 이 오류는 정책 설정에 포함 되지 않습니다 VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun 레지스트리 키 아래에서이 사용자 계정에 대해 허용 된 창 프로그램으로 나타납니다.  
  
 자세한 내용은 다음을 참조 합니다.  
  
-   사용할 수 있는 기술 자료 문서, 324153 [http://support.microsoft.com/default.aspx?scid=kb;en-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153)합니다.  
  
-   [시스템 정책 설정 준수](http://msdn.microsoft.com/library/aa372139), "허용 된 Windows 응용 프로그램 실행" 섹션.