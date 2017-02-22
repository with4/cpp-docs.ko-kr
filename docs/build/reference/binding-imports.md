---
title: "가져오기 바인딩 | Microsoft Docs"
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
  - "/DELAY:NOBIND 링커 옵션"
  - "DELAY:NOBIND 링커 옵션"
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 가져오기 바인딩
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커의 기본 동작은 지연 로드된 DLL에 대해 바인딩 가능한 IAT\(가져오기 주소 테이블\)를 만드는 것입니다.  DLL이 바인딩되면 도우미 함수는 참조되는 각 가져오기마다 **GetProcAddress**를 호출하는 대신 바인딩된 정보를 사용합니다.  이 때 타임스탬프나 기본 설정 주소가 로드된 DLL과 일치하지 않으면 도우미 함수는 바인딩된 IAT\(가져오기 주소 테이블\)가 변경된 것으로 간주하고 바인딩된 IAT가 없는 것처럼 처리합니다.  
  
 DLL의 지연 로드된 가져오기를 바인딩하지 않으려는 경우 링커의 명령줄에서 [\/DELAY](../../build/reference/delay-delay-load-import-settings.md):nobind를 지정하면 바인딩된 IAT가 생성되지 않으므로 이미지 파일의 공간이 소모되지 않습니다.  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)