---
title: "스트림 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Controlling Streams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "스트림 제어"
  - "스트림"
  - "스트림, 제어"
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 스트림 제어
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[fopen](../c-runtime-library/reference/fopen-wfopen.md) 는 `FILE` 형식의 개체 주소를 반환합니다.  열린 파일에서 이 주소를 다양한 라이브러리 함수에 대한 `stream` 인수로 사용하여 몇가지 작업을 수행합니다.  바이트 스트림에 대해, [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md) 를 호출하여 각 문자를 읽은 경우 모든 입력이 발생합니다. 그리고 모든 출력은 [fputc](../c-runtime-library/reference/fputc-fputwc.md) 를 호출하여 각 문자를 쓴 경우 발생합니다.  와이드 스트림에 대해, [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md) 를 호출하여 각 문자를 읽은 경우 모든 입력이 발생합니다. 그리고 모든 출력은 [fputwc](../c-runtime-library/reference/fputc-fputwc.md) 를 호출하여 각 문자를 쓴 경우 발생합니다.  
  
 `FILE` 개체의 주소가 유효하지 않은 경우 [fclose](../c-runtime-library/reference/fclose-fcloseall.md) 를 호출하여 파일을 닫을 수 있습니다.  
  
 `FILE` 개체는 스트림의 상태를 저장합니다 :  
  
-   오류 표시자는 읽기 또는 쓰기 오류를 발견한 함수에 의해 0이 아닌 값으로 설정됩니다.  
  
-   파일의 끝 표시자는 읽는 동안 파일의 끝을 발견 한 함수에 의해 0이 아닌 값으로 설정됩니다.  
  
-   파일 위치 요청을 지원할 수있는 경우 파일 위치 표시자는 읽기 및 쓰기 스트림 내의 다음의 바이트를 지정합니다.  
  
-   [stream state](../c-runtime-library/stream-states.md) 는 스트림이 읽기나 쓰기를 허용하는지 여부와 스트림이 바운드 인지, 바이트 지향인지, 와이드 지향인지를 지정합니다.  
  
-   변환 상태는 부분적으로 파일의 바이트의 시퀀스에 대한 상태 이동뿐만 아니라 어셈블 되거나 일반적으로 생성된 멀티 바이트 문자의 상태를 기억합니다.  
  
-   파일 버퍼는 스트림에 대해 라이브러리 함수를 사용하여 읽기와 쓰기 작업의 성능을 향상시킬 수 있는 주소와 배열 개체의 사이즈를 지정합니다.  
  
 개체를 사용하여 지정한 `FILE` 개체 또는 파일 버퍼에 저장된 값을 바꾸지 마십시오.  `FILE` 개체를 복사할 수 없으며, 복사된 주소를 라이브러리 함수에 대해 일시적으로 `stream` 인수로 사용할 수 있습니다.  
  
## 참고 항목  
 [파일 및 스트림](../c-runtime-library/files-and-streams.md)