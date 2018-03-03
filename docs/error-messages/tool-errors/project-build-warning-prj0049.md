---
title: "프로젝트 빌드 경고 PRJ0049 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f87bc7e26fd7cc50defbc086594c92a3ea339ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0049"></a>프로젝트 빌드 경고 PRJ0049
참조 된 대상 '\<참조 >'을 실행 하려면.NET \<MinFrameworkVersion > 하며이 프로젝트의 대상 프레임 워크에서 실행 되지 것입니다  
  
 Visual Studio 2008을 사용 하 여 만든 응용 프로그램의 버전을 지정할 수는 [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] 대상입니다. 어셈블리 또는 프로젝트의 버전에 따라 달라 지에 대 한 참조를 추가 하는 경우는 [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] 대상된 버전 보다 이후 이면 컴파일 타임에이 경고가 발생 합니다.  
  
### <a name="to-correct-this-warning"></a>이 경고를 해결 하려면  
  
1.  다음 중 하나를 선택합니다.  
  
    -   프로젝트의 대상된 프레임 워크를 변경 **속성 페이지** 대화 상자를 보다 높거나 같은 참조 되는 모든 어셈블리와 프로젝트의 최소 프레임 워크 버전입니다. 자세한 내용은 참조 [참조 추가](../../ide/adding-references-in-visual-cpp-projects.md)합니다.  
  
    -   어셈블리 또는 프로젝트 대상된 프레임 워크 보다 최신인 최소 프레임 워크 버전에 대 한 참조를 제거 합니다. 이러한 항목은 프로젝트의 경고 아이콘으로 표시 됩니다 **속성 페이지**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 빌드 오류 및 경고(PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)