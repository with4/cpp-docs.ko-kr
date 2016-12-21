---
title: "명령줄 경고 D9025 | Microsoft Docs"
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
  - "D9025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9025"
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄 경고 D9025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option1'을\(를\) 'option2'\(으\)로 재정의합니다.  
  
 *option1* 옵션은 지정되었으나 *option2*에 의해 재정의되었습니다.  *option2* 옵션을 사용했습니다.  
  
 두 옵션이 모순되거나 호환되지 않는 지시문을 지정한 경우 명령줄에서 오른쪽에서 가장 멀리 있는 옵션에 지정되었거나 암시된 지시문이 사용됩니다.  
  
 개발 환경에서 컴파일할 때 이 경고가 발생했지만 충돌하는 옵션이 어디에 있는지 알 수 없으면 다음 설명을 참조하십시오.  
  
-   옵션은 코드나 프로젝트의 설정에서 지정할 수 있습니다.  컴파일러의 [명령줄 속성 페이지](../../ide/command-line-property-pages.md)를 살펴본 결과 **모든 옵션** 필드에서 충돌하는 옵션을 발견하면 이 옵션이 프로젝트의 속성 페이지에 설정되어 있는 것이고, 그렇지 않으면 옵션이 소스 코드에 설정되어 있는 것입니다.  
  
     옵션이 프로젝트의 속성 페이지에 설정되어 있으면 솔루션 탐색기에서 프로젝트 노드를 선택하고 컴파일러의 전처리기 속성 페이지를 검토하십시오.  여기서 설정된 옵션을 찾지 못하면 솔루션 탐색기에서 각 소스 코드 파일에 대한 전처리기 속성 페이지 설정을 검사하여 옵션이 추가되지 않았는지 확인하십시오.  
  
     코드에 설정되어 있는 옵션은 코드나 창 헤더에 설정되었을 수 있습니다.  [\/P](../../build/reference/p-preprocess-to-a-file.md)를 사용하여 전처리된 파일을 만들고 기호를 검색해 보십시오.