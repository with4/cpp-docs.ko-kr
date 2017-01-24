---
title: "바이트 및 와이드 스트림 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Byte and Wide Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "byte 함수"
  - "와이드 스트림"
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 바이트 및 와이드 스트림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

바이트 스트림은 바이트의 시퀀스로 파일을 처리합니다.  프로그램 내에서 스트림은 바이트의 시퀀스와 동일합니다.  
  
 반면, 와이드 스트림은 파일을 다양한 인코딩 규칙을 가질 수 있는 일반화된 멀티 바이트 문자로 처리합니다. \(이전에 설명한 대로 텍스트 및 이진 파일은 여전히 읽히고 작성됩니다.\) 프로그램에서 스트림은 상응하는 와이드 문자의 시퀀스와 유사합니다.  두 표현 사이의 변환은 표준 C 라이브러리 내에서 발생합니다.  변환 규칙은 원칙적으로 `LC_CTYPE` 범주를 변경하는 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 호출하여 변경할 수 있습니다.  와이드 스트림은 와이드 기반이 될 때 이 변환 규칙을 지정하며 `LC_CTYPE` 범주가 이후에 변경되더라도 이러한 규칙을 유지합니다.  
  
 와이드 스트림 내에서의 위치 지정은 텍스트 스트림와 동일한 제한을 갖습니다.  또한 파일 위치 표시기도 상태에 따라 다른 인코딩을 처리해야 할 수 있습니다.  일반적으로, 이는 스트림 내의 바이트 오프셋과 `mbstate_t` 형식의 개체를 모두 포함합니다.  따라서, 와이드 스트림에서 유일하게 신뢰할 수 있는 파일 위치를 얻을 수 있는 방법은 [fgetpos](../c-runtime-library/reference/fgetpos.md)를 호출하는 것이며, 이렇게 얻은 위치를 다시 저장하는 유일하게 신뢰할 수 있는 방법은 [fsetpos](../c-runtime-library/reference/fsetpos.md)를 호출하는 것입니다.  
  
## 참고 항목  
 [파일 및 스트림](../c-runtime-library/files-and-streams.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)