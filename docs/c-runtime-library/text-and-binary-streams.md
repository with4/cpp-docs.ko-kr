---
title: "텍스트 및 이진 스트림 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "이진 스트림"
  - "텍스트 스트림"
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 텍스트 및 이진 스트림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

텍스트 스트림은 텍스트 기반 디스플레이에 쓰여서 읽을 수 있도록 하나 이상의 텍스트 줄로 구성됩니다.  텍스트 스트림을 읽을 때 프로그램은 각 줄의 끝에서 `NL` \(줄 바꿈\)을 읽습니다.  텍스트 스트림에 기록할 때, 프로그램은 줄의 끝에 `NL` 기호를 기록합니다.  대상 환경의 서로 다른 규칙에 맞게 하기 위하여, 파일에서 텍스트를 표현할 때 라이브러리 함수는 프로그램과 텍스트 스트림 사이에 전송되는 문자의 수를 변경할 수 있습니다.  
  
 따라서, 텍스트 스트림에서 위치 지정이 제한됩니다.  [fgetpos](../c-runtime-library/reference/fgetpos.md) 또는 [ftell](../c-runtime-library/reference/ftell-ftelli64.md)을 호출하여 현재 파일 위치 표시기를 얻을 수 있습니다.  [fsetpos](../c-runtime-library/reference/fsetpos.md) 또는 [fseek](../c-runtime-library/reference/fseek-fseeki64.md)를 호출하여 이런 방법으로 얻은 위치 또는 스트림의 처음이나 끝으로 텍스트 스트림을 위치시킬 수 있습니다.  모든 다른 위치의 변경은 지원되지 않습니다.  
  
 최대 이식성을 위하여, 프로그램은 쓰지 않아야 합니다.  
  
-   빈 파일입니다.  
  
-   줄 끝의 공백 문자입니다.  
  
-   줄의 부분\(파일 끝의 `NL`을 제외하여\)입니다.  
  
-   인쇄 가능한 문자와는 다른 문자인, NL 및 `HT`\(수평 탭\)입니다.  
  
 이러한 규칙을 따르는 경우, 텍스트 스트림에서 읽은 문자 시퀀스\(바이트나 멀티 바이트 문자로\)는 파일을 만들 때 텍스트 스트림에 쓴 문자의 시퀀스와 일치합니다.  그렇지 않으면, 라이브러리 함수는 파일을 닫을 때 파일이 비어 있는 경우 만든 파일을 제거할 수 있습니다.  또는 파일에 쓸 문자를 삭제하거나 변경할 수 있습니다.  
  
 이진 스트림은 하나 이상 바이트의 임의의 정보로 구성됩니다.  임의의 개체에 저장된 값을 이진 스트림에 쓰고 \(바이트 기반으로\), 이를 쓸 때 해당 개체에 무엇이 저장되었는지를 정확하게 읽을 수 있습니다.  라이브러리 함수는 프로그램과 이진 스트림 사이에 전송된 바이트를 변경하지 않습니다.  그러나 그들은, 이진 스트림으로 쓴 파일에 널 바이트의 임의의 수를 추가합니다.  프로그램은 이진 스트림이 끝에서 이러한 추가 널 바이트를 처리해야 합니다.  
  
 따라서, 이진 스트림의 끝을 기준으로 한 상대적 위치 지정을 제외하고는 스트림 내의 위치 지정은 잘 정의됩니다.  텍스트 스트림과 동일하게 현재 파일 위치 표시기를 얻고 변경할 수 있습니다.  더욱이, [ftell](../c-runtime-library/reference/ftell-ftelli64.md) 및 [fseek](../c-runtime-library/reference/fseek-fseeki64.md)에서 사용되는 오프셋은 바이트를 스트림의 시작\(0 바이트\)에서부터 세기 때문에, 이러한 오프셋에서의 정수 산술 연산은 예측 가능한 결과를 도출합니다.  
  
 바이트 스트림은 바이트의 시퀀스로 파일을 처리합니다.  프로그램에서, 스트림은 위에 설명된 가능한 변경을 제외하고는 바이트의 시퀀스와 같습니다.  
  
## 참고 항목  
 [파일 및 스트림](../c-runtime-library/files-and-streams.md)