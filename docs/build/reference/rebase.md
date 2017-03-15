---
title: "/REBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rebase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/REBASE editbin 옵션[C++]"
  - "기준 주소[C++]"
  - "DLL[C++], 링크"
  - "실행 파일[C++], 기준 주소"
  - "REBASE editbin 옵션"
  - "-REBASE editbin 옵션"
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /REBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/REBASE[:modifiers]  
```  
  
## 설명  
 이 옵션은 지정된 파일의 기준 주소를 설정합니다.  EDITBIN은 각 파일의 크기에 따라 연속적인 주소 공간에서 가장 가까운 64KB 메모리 블록으로 반올림하여 새 기준 주소를 할당합니다.  기준 주소에 대한 자세한 내용은 [기준 주소](../../build/reference/base-base-address.md)\(\/BASE\) 링커 옵션을 참조하십시오.  
  
 EDITBIN 명령줄에서 기준 주소의 순서에 따라 *files* 인수에 프로그램의 실행 파일 및 DLL을 지정합니다.  선택적으로 하나 이상의 *modifiers*를 쉼표\(**,**\)로 구분하여 지정할 수 있습니다.  
  
|한정자|작업|  
|---------|--------|  
|BASE**\=***address*|파일에 기준 주소를 다시 할당하기 위해 시작 주소를 제공합니다.  10진법 또는 C 언어 표기법으로 *address*를 지정합니다.  BASE를 지정하지 않은 경우 기본적으로 시작하는 기준 주소는 0x400000입니다.  DOWN을 사용한다면 반드시 BASE를 지정해야 하며 *address*는 기준 주소 범위의 끝을 설정합니다.|  
|BASEFILE|이름이 COFFBASE.TXT인 파일을 만듭니다. 이 파일은 LINK의 \/BASE 옵션에서 필요한 형식의 텍스트 파일입니다.|  
|아래쪽 화살표|끝 주소에서 아래쪽으로 기준 주소를 다시 할당하도록 EDITBIN에 지시합니다.  첫 번째 파일이 주소 범위의 끝 이하에서 사용할 수 있는 최상위 주소에 배치되는 순서로 파일을 다시 할당합니다.  파일의 기준 주소 배치에 충분한 주소 공간을 보장하려면 DOWN과 함께 BASE를 사용해야 합니다.  지정된 파일에 필요한 주소 공간을 결정하려면 파일에 \/REBASE를 지정하여 EDITBIN을 실행하고 나타난 전체 크기에 64KB를 더합니다.|  
  
## 참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)