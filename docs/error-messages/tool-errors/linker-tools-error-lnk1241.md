---
title: "링커 도구 오류 LNK1241 | Microsoft Docs"
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
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

resource file 리소스 파일이 이미 지정되었습니다.  
  
 명령줄에서 수동으로 **cvtres**를 실행하고 이로 인해 생성된 .obj 파일을 링커와 다른 .res 파일에 전달하면 이 오류가 발생합니다.  
  
 .res 파일을 여러 개 지정하려면 이 파일들을 모두 **cvtres**에 의해 만들어진 .obj 파일 내에서가 아니라 링커에 .res 파일로서 전달하십시오.