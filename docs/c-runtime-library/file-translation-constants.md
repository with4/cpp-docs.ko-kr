---
title: "파일 변환 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상수[C++], 파일 변환 모드"
  - "파일 변환[C++]"
  - "파일 변환[C++], 상수"
  - "변환 상수"
  - "변환, 상수"
  - "변환, 파일 변환 상수"
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 파일 변환 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <stdio.h>  
```  
  
## 설명  
 이 상수들은 변환 모드\(**"b"** 또는 **"t"**\)를 지정합니다.  이 모드는 액세스 유형\(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\)을 지정하는 문자열에 포함됩니다.  
  
 변환 모드는 다음과 같습니다.  
  
 **t**  
 텍스트\(변환됨\) 모드에서 엽니다.  이 모드에서 캐리지 리턴\/줄 바꿈 \(CR\-LF\) 조합은 입력에서 단일 줄 바꿈\(LF\)으로 변환되고, 줄 바꿈 문자는 출력에서 캐리지 리턴\/줄 바꿈 조합으로 변환됩니다.  또한, CTRL \+ Z는 입력에서 파일 끝 문자로 해석 됩니다.  읽기\/쓰기를 위해 연 파일에서 `fopen`은 파일 끝에서 Ctrl\+Z를 확인하여 제거합니다\(가능한 경우\).  `fseek` 및 `ftell`을 사용하여 Ctrl\+Z로 끝나는 파일 내에서 이동하면 파일의 끝 부분에서 `fseek`가 제대로 동작하지 않을 수 있으므로 이 작업을 수행합니다.  
  
> [!NOTE]
>  **t** 옵션은 `fopen` 및 `freopen`의 ANSI 표준에 속하지 않습니다.  이는 Microsoft 확장이며 ANSI 이식성이 요구되는 곳에 사용될 수 없습니다.  
  
 **b**  
 이진\(변환되지 않은\) 모드에서 열립니다.  위의 변환이 억제됩니다.  
  
 **t** 또는 **b**가 *mode*에 지정되지 않은 경우, 기본 변환 모드는 [\_fmode](../c-runtime-library/fmode.md) 변수로 정의됩니다.  텍스트 및 이진 모드를 사용하는 방법에 대한 자세한 내용은 [Text and Binary Mode File I\/O](../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하십시오.  
  
## 참고 항목  
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [전역 상수](../c-runtime-library/global-constants.md)