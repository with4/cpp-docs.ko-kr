---
title: "컴파일러 오류 C3505 | Microsoft Docs"
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
  - "C3505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3505"
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'guid' 형식 라이브러리를 로드할 수 없습니다.  
  
 C3505는 64비트 컴퓨터에서 32비트에서 64비트로의 크로스 컴파일러를 실행하는 경우에 발생할 수 있습니다. 컴파일러가 WOW64에서 실행되고 있지만 32비트 레지스트리 하이브에서만 읽을 수 있기 때문입니다.  
  
 이 C3505를 해결하려면 가져오려는 형식 라이브러리의 32비트 버전과 64비트 버전을 빌드하고 두 버전을 모두 등록해야 합니다.  또는 네이티브 64비트 컴파일러를 사용할 수도 있지만 이 경우 IDE에서 64비트 컴파일러를 가리키도록 VC\+\+ 디렉터리를 변경해야 합니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [방법: 명령줄에서 64비트 Visual C\+\+ 도구 집합 활성화](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [방법: 명령줄에서 64비트 Visual C\+\+ 도구 집합 활성화](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [방법: 64비트 플랫폼을 대상으로 한 Visual C\+\+ 프로젝트 구성](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)