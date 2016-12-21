---
title: "링커 도구 경고 LNK4075 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4075"
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"option1"이\(가\) "option2" 사양으로 인해 무시됩니다.  
  
 둘째 옵션이 첫째 옵션을 재정의합니다.  
  
 함께 사용할 수 없는 링커 옵션을 동시에 지정했습니다.  링커 옵션을 확인하십시오.  링커 옵션을 지정하는 위치는 프로젝트를 빌드하는 방식에 따라 달라집니다.  
  
-   개발 환경에서 빌드하는 경우 프로젝트의 링커 속성 페이지에서 두 링커 옵션이 지정된 위치를 확인해야 합니다.  자세한 내용은 [방법: 속성 페이지로 프로젝트 속성 지정](../../misc/how-to-specify-project-properties-with-property-pages.md)을 참조하십시오.  
  
-   명령줄에서 빌드하는 경우 명령줄에 지정된 링커 옵션을 확인하십시오.  
  
-   빌드 스크립트를 사용하여 빌드하는 경우 스크립트에서 해당 링커 옵션이 지정된 위치를 확인하십시오.  
  
 함께 사용할 수 없는 링커 옵션이 동시에 지정된 위치를 찾은 다음 해당 링커 옵션 중 하나를 제거합니다.  
  
 다음은 몇 가지 예제입니다.  
  
-   \/EDITANDCONTINUE라는 내부 링커 옵션이 내포된 **\/ZI**를 사용하여 컴파일한 모듈과 \/EDITANDCONTINUE가 내포되지 않은 \/OPT:REF, \/OPT:ICF 또는 \/INCREMENTAL:NO를 사용하여 컴파일한 모듈을 링크하면 LNK4075가 발생합니다.  자세한 내용은 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md)를 참조하십시오.