---
title: "프로젝트 빌드 경고 PRJ0049 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0049"
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 경고 PRJ0049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

참조된 대상 '\<Reference\>'은\(는\) .NET Framework \<MinFrameworkVersion\>이상에서 실행해야 하며, 이 프로젝트의 현재 대상 프레임워크에서는 실행되지 않습니다.  
  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]을 사용하여 만든 응용 프로그램에서는 해당 응용 프로그램의 대상 [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] 버전을 지정할 수 있습니다.  대상 버전보다 최신 버전의 [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)]가 있어야 하는 어셈블리나 프로젝트에 대한 참조를 추가하면 컴파일 타임에 이 경고가 발생합니다.  
  
### 이 경고를 해결하려면  
  
1.  다음 중 하나를 선택합니다.  
  
    -   프로젝트의 **속성 페이지** 대화 상자에서 대상 프레임워크를 참조된 모든 어셈블리 및 프로젝트의 최소 프레임워크 버전보다 높거나 같게 변경합니다.  자세한 내용은 [참조 추가](../../ide/adding-references-in-visual-cpp-projects.md)을 참조하십시오.  
  
    -   최소 프레임워크 버전이 대상 프레임워크보다 높은 어셈블리나 프로젝트에 대한 참조를 제거합니다.  이러한 항목은 프로젝트의 **속성 페이지**에 경고 아이콘으로 표시됩니다.  
  
## 참고 항목  
 [프로젝트 빌드 오류 및 경고\(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)