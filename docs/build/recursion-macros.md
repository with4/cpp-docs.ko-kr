---
title: "재귀 매크로 | Microsoft Docs"
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
  - "매크로, 재귀"
  - "NMAKE 프로그램, 재귀 매크로"
  - "재귀 매크로"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 재귀 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE를 재귀적으로 호출하려면 재귀 매크로를 사용합니다.  재귀 세션은 명령줄과 환경 변수 매크로 및Tools.ini 정보를 상속하고  메이크파일에 정의된 유추 규칙이나 **.SUFFIXES** 및 **.PRECIOUS** 사양은 상속하지 않습니다.  재귀적 NMAKE 세션에 매크로를 전달하려면 NMAKE가 재귀적으로 호출되기 전에 SET를 사용하여 환경 변수를 설정하거나 Tools.ini에 매크로를 정의합니다.  
  
|매크로|정의|  
|---------|--------|  
|**MAKE**|원래 NMAKE를 호출하는 데 사용하는 명령입니다.<br /><br /> $\(MAKE\) 매크로는 nmake.exe에 전체 경로를 전달합니다.|  
|**MAKEDIR**|NMAKE가 호출될 때 현재 디렉터리입니다.|  
|**MAKEFLAGS**|현재 적용된 옵션입니다.  `/$(MAKEFLAGS)`로 사용합니다.  \/F는 포함되지 않습니다.|  
  
## 참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)