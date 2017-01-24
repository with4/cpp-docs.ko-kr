---
title: "링커 도구 오류 LNK1112 | Microsoft Docs"
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
  - "LNK1112"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1112"
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1112
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' 모듈 컴퓨터 종류가 'type2' 대상 컴퓨터 종류와 충돌합니다.  
  
 입력으로 지정된 개체 파일이 다른 종류의 컴퓨터용으로 컴파일되었습니다.  
  
 예를 들어 **\/clr**로 컴파일된 개체 파일 및 **\/clr:pure**\(컴퓨터 종류 CEE\)로 컴파일된 개체 파일을 연결하려고 하면 링커에서 오류 LNK1112를 생성합니다.  
  
 마찬가지로 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러를 사용하여 하나의 모듈을 만들고 x86 컴파일러를 사용하여 다른 모듈을 만든 경우 연결하려고 하면 링커에서 LNK1112를 생성합니다.  
  
 이 오류는 64비트 응용 프로그램을 개발하고 있지만 Visual C\+\+ 64비트 컴파일러 중 하나를 설치하지 않은 경우에 발생할 수 있습니다. 이런 경우 64비트 구성을 사용할 수 없습니다. 이 문제를 해결하려면 Visual Studio 설치 관리자를 실행하고 누락된 C\+\+ 구성 요소를 설치하세요.  
  
 또한 이 오류는 **Configuration Manager**에서 **활성 솔루션 구성**을 변경한 다음 중간 프로젝트 파일을 삭제하기 전에 프로젝트를 빌드하려고 하면 발생할 수 있습니다. 이 오류를 해결하려면 **빌드** 메뉴에서 **솔루션 다시 빌드**를 선택합니다.**빌드** 메뉴에서 **솔루션 정리**를 선택한 다음 솔루션을 빌드할 수도 있습니다.  
  
## 참고 항목  
 [링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)