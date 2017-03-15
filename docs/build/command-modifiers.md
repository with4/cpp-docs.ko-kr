---
title: "명령 한정자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령 한정자"
  - "NMAKE 프로그램, 명령 한정자"
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 명령 한정자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명령 앞에 하나 이상의 명령 한정자를 지정할 수 있으며 공백이나 탭으로 구분할 수도 있습니다.  명령과 같이 한정자도 들여써야 합니다.  
  
|한정자|용도|  
|---------|--------|  
|@*command*|명령을 표시하지 않습니다.  명령으로 표시할 수는 있습니다.  기본적으로, NMAKE는 실행된 모든 명령을 화면에 표시합니다.  메이크파일 전체를 표시하지 않으려면 \/S를 사용하고 메이크파일의 일부를 표시하지 않으려면 **.SILENT**를 사용합니다.|  
|**–**\[`number` \]*command*|*command*에 대한 오류 확인을 해제합니다.  기본적으로 명령이 0이 아닌 종료 코드를 반환하면 NMAKE가 중지됩니다.  –`number`를 사용한 경우 종료 코드가 `number` 보다 크면 NMAKE가 중지됩니다.  대시와 숫자 사이에 공백이나 탭을 사용할 수 없습니다.`number`와 *command* 사이에 공백이나 탭을 하나 이상 사용해야 합니다.  메이크파일 전체에 대한 오류 확인을 해제하려면 \/I를 사용하고 메이크파일의 일부에 대한 오류 확인을 해제하려면 **.IGNORE**를 사용합니다.|  
|**\!** *command*|*command*가 **$\*\***\(종속 줄의 모든 종속 파일\) 또는 **$?**\(타임스탬프가 대상보다 이후인 종속 줄의 모든 종속 파일\)를 사용하는 경우 각 종속 파일에 대한 *command*를 실행합니다.|  
  
## 참고 항목  
 [메이크파일의 명령](../build/commands-in-a-makefile.md)