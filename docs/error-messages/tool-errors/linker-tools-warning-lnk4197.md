---
title: "링커 도구 경고 LNK4197 | Microsoft Docs"
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
  - "LNK4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4197"
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exportname' 내보내기가 여러 번 지정되었습니다. 첫째 사양을 사용합니다.  
  
 내보내기가 다른 방법으로 여러 번 지정되었습니다.  링커는 첫째 사양을 사용하며 나머지 사양은 무시합니다.  
  
 C 런타임 라이브러리를 다시 빌드하는 중이면 이 메시지를 무시해도 됩니다.  
  
 내보내기가 똑같은 방식으로 여러 번 지정된 경우에는 링커가 경고를 발생시키지 않습니다.  
  
 예를 들어, 다음 .def 파일 내용은 이 경고를 발생시킵니다.  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  동일한 내보내기가 명령줄\(export: 구문을 통해\)과 .def 파일에 모두 지정되었습니다.  
  
2.  동일한 내보내기가 .def 파일에서 서로 다른 특성을 사용하여 두 번 표시되었습니다.