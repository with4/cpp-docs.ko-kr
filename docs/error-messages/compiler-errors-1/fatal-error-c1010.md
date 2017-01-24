---
title: "심각한 오류 C1010 | Microsoft Docs"
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
  - "C1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1010"
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더를 찾는 동안 예기치 않은 파일의 끝이 나타났습니다.'\#include name'을\(를\) 소스에 추가하시겠습니까?  
  
 [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)로 지정된 포함 파일이 소스 파일에 나타나지 않습니다.  이 옵션은 대부분의 Visual C\+\+ 프로젝트 형식에서 기본적으로 활성화되어 있으며 "stdafx.h"는 이 옵션에 지정된 기본 포함 파일입니다.  
  
 Visual Studio 환경에서 이 오류를 해결하려면 다음 방법 중 하나를 사용하십시오.  
  
-   프로젝트에 미리 컴파일된 헤더를 사용하지 않는 경우 소스 파일의 **미리 컴파일된 헤더 만들기\/사용** 속성을 **미리 컴파일된 헤더 사용 안 함**으로 설정합니다.  이 컴파일러 옵션을 설정하려면 다음 단계를 따릅니다.  
  
    1.  프로젝트의 솔루션 탐색기 창에서 마우스 오른쪽 단추로 프로젝트 이름을 클릭한 다음 **속성**을 클릭합니다.  
  
    2.  왼쪽 창에서 **C\/C\+\+** 폴더를 클릭합니다.  
  
    3.  **미리 컴파일된 헤더** 노드를 클릭합니다.  
  
    4.  오른쪽 창에서 **미리 컴파일된 헤더 만들기\/사용**을 클릭한 다음 **미리 컴파일된 헤더 사용 안 함**을 클릭합니다.  
  
-   현재 프로젝트에서 헤더 파일을 실수로 삭제, 이름 변경 또는 제거하지 않았는지 확인합니다. 이 파일은 기본적으로 stdafx.h입니다.  또한 **\#include "stdafx.h"**를 사용하여 이 파일을 소스 파일의 다른 모든 코드 앞에 추가해야 합니다. 이 헤더 파일을 지정하는 데는 **파일에서 PCH 만들기\/사용** 프로젝트 속성을 사용합니다.