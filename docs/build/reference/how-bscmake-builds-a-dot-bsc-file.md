---
title: "BSCMAKE에서 .Bsc 파일을 빌드하는 방법 | Microsoft Docs"
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
  - "찾아보기 정보 파일(.bsc), 빌드"
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE에서 .Bsc 파일을 빌드하는 방법
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE는 가능한 가장 효율적인 방법으로 .bsc 파일을 빌드하거나 다시 빌드합니다.  나중에 문제가 발생하지 않도록 빌드 과정을 이해하는 것이 중요합니다.  
  
 BSCMAKE는 찾아보기 정보 파일을 빌드할 때 .sbr 파일의 길이를 0으로 자릅니다.  다음에 같은 파일을 빌드하는 동안 길이가 0인\(또는 빈\) .sbr 파일은 BSCMAKE에게 해당 .sbr 파일에 구성할 새로운 정보가 없음을 알려 줍니다.  따라서 BSCMAKE는 파일에서 해당 부분을 업데이트할 필요가 없고 증분 빌드만으로도 충분하다는 것을 알 수 있습니다.  모든 빌드를 수행하는 동안\(\/n 옵션을 지정하지 않은 경우\) BSCMAKE는 먼저 변경된 .sbr 파일만 사용하여 파일에 대해 증분 업데이트를 시도합니다.  
  
 BSCMAKE는 \/o 옵션으로 지정된 이름을 가진 .bsc 파일을 찾습니다.  \/o 옵션을 지정하지 않은 경우 BSCMAKE는 첫째 .sbr 파일의 기본 이름과 .bsc 확장명을 가진 파일을 찾습니다.  해당하는 파일이 있으면 BSCMAKE는 관련된 .sbr 파일만 사용하여 찾아보기 정보 파일의 증분 빌드를 수행합니다.  그러나 해당하는 파일이 없는 경우 BSCMAKE는 모든 .sbr 파일을 사용하여 전체 빌드를 수행합니다.  빌드 규칙은 다음과 같습니다.  
  
-   전체 빌드를 제대로 수행하려면 지정된 모든 .sbr 파일이 있어야 하고 이 파일들은 잘리지 않아야 합니다.  .sbr 파일이 잘리면 BSCMAKE를 실행하기 전에 다시 컴파일하거나 어셈블링하여 파일을 다시 빌드해야 합니다.  
  
-   증분 빌드를 제대로 수행하려면 .bsc 파일이 있어야 합니다.  빈 파일을 포함하여 관련된 모든 .sbr 파일이 있어야 하고 이 파일들을 BSCMAKE 명령줄에 지정해야 합니다.  명령줄에서 .sbr 파일을 생략하는 경우 BSCMAKE는 해당 파일의 구성 정보를 제거합니다.  
  
## 참고 항목  
 [.Bsc 파일 빌드](../../build/reference/building-a-dot-bsc-file.md)