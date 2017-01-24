---
title: "찾아보기 정보 파일 빌드: 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".bsc 파일, .bsc 파일 정보"
  - "찾아보기 정보 파일(.bsc)"
  - "찾아보기 정보 파일(.bsc), 만들기"
  - "bsc 파일, bsc 파일 정보"
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 찾아보기 정보 파일 빌드: 개요
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기호 검색에 사용할 찾아보기 정보를 만들기 위해 컴파일러를 사용하여 프로젝트에서 각 소스 파일의 .sbr 파일을 만든 다음 BSCMAKE.EXE를 실행하여 .sbr 파일을 하나의 .bsc 파일로 연결합니다.  
  
 .sbr 파일과 .bsc 파일을 만드는 데 시간이 소요되므로 Visual C\+\+는 기본적으로 이 기능을 해제합니다.  현재 정보를 찾아보려면 찾아보기 옵션을 설정하고 프로젝트를 다시 빌드해야 합니다.  
  
 컴파일러에서 .sbr 파일을 만들도록 하려면 [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 또는 [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)를 사용합니다.  .bsc 파일을 만들려면 명령줄에서 [BSCMAKE](../../build/reference/bscmake-command-line.md)를 호출하면 됩니다.  명령줄에서 BSCMAKE를 사용하면 찾아보기 정보 파일 조작을 더 세부적으로 제어할 수 있습니다.  자세한 내용은 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)를 참조하십시오.  
  
> [!TIP]
>  .bsc 파일은 생성하지 않고 .sbr 파일만 생성하도록 설정할 수 있습니다.  이렇게 하면 빌드 속도가 빨라지지만 .bsc 파일 생성을 설정하고 프로젝트를 빌드해도 새 .bsc 파일을 신속하게 만들 수 있습니다.  
  
 .bsc 파일의 크기를 줄이면 .bsc 파일을 빌드하는 데 필요한 시간, 메모리 및 디스크 공간을 절약할 수 있습니다.  
  
 개발 환경에서 브라우저 파일을 빌드하는 방법에 대한 내용은 [일반 속성 페이지\(프로젝트\)](../../ide/general-property-page-project.md)를 참조하십시오.  
  
### 크기가 작은 .bsc 파일을 만들려면  
  
1.  [BSCMAKE 명령줄 옵션](../../build/reference/bscmake-options.md)을 사용하여 찾아보기 정보 파일에서 정보를 제외시킵니다.  
  
2.  컴파일 또는 어셈블링할 때 하나 이상의 .sbr 파일에서 로컬 기호를 생략합니다.  
  
3.  개체 파일에 현재 디버깅 단계에 필요한 정보가 포함되어 있지 않은 경우 찾아보기 정보 파일을 다시 빌드할 때 BSCMAKE 명령에서 해당 .sbr 파일을 생략합니다.  
  
### 여러 프로젝트의 찾아보기 정보를 브라우저 파일 \(.bsc\) 하나로 결합하려면  
  
1.  프로젝트 수준에서 .bsc 파일을 빌드하지 않거나 \/n 스위치를 사용하여 .sbr 파일이 잘리지 않게 합니다.  
  
2.  모든 프로젝트를 빌드한 후 전체 .sbr 파일을 입력으로 사용하여 BSCMAKE를 실행합니다.  이 때 와일드카드를 사용할 수 있습니다.  예를 들어 C:\\X, C:\\Y 및 C:\\Z 프로젝트 디렉터리에 있는 .sbr 파일들을 하나의 .bsc 파일로 결합하려는 경우 BSCMAKE C:\\X\\\*.sbr C:\\Y\\\*.sbr C:\\Z\\\*.sbr \/o c:\\whatever\_directory\\combined.bsc를 사용하여 하나로 결합된 .bsc 파일을 빌드할 수 있습니다.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)