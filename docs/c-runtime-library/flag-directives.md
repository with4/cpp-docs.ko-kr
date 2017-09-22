---
title: "플래그 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "플래그 지시문 printf 함수"
  - "printf 함수의 형식 사양 필드"
  - "인쇄 플래그 지시문"
  - "printf 함수, 형식 사양 필드"
ms.assetid: b00cbdc9-1e5c-4b30-9f56-c1ef8d383767
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 플래그 지시문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 지정에서, 첫 번째 선택적 필드는 `flags`입니다.  플래그 지시문은 출력 근거 및 출력 기호, 공백, 선행되는 0, 소수점 및 8 진수 및 16 진수 접두사를 지정 하는 문자입니다.  둘 이상의 플래그 지시문은 형식 지정 사양에 나타날 수 있고 플래그는 임의의 순서로 나타날 수 있습니다.  
  
### 플래그 문자  
  
|플래그|의미|기본|  
|---------|--------|--------|  
|`–`|주어진 필드 너비내에서 결과를 왼쪽에 정렬합니다.|오른쪽 정렬.|  
|`+`|만일 부호가 있는 형식인 경우, 출력의 접두사로 부호\(\+ 또는 \-\)를 사용합니다.|부호는 오직 \(\-\) 음수인 부호 있는 값에 대해서만 나타납니다.|  
|`0`|만일 `width` 가 `0` 으로 지정된 경우, 최소 너비에 도달할때까지 선행되는 0이 추가됩니다.  만일 `0` 과 `–` 모두 나타나는 경우, `0` 은 무시됩니다.  만일 `0` 이 정수 형식으로 지정되는 경우\(`i`, `u`, `x`, `X`, `o`, `d`\), 정밀에 대한 사양 지정됩니다.—예를 들어, `%04.d`—`0` 은 무시됩니다.|패딩이 없습니다.|  
|공백 \(' '\)|만일 부호가 있고 양수이면, 출력값의 접두사로 공백이 사용됩니다.  만일 공백과 \+ 플래그가 모두 나타나면, 공백은 무시됩니다.|공백 없이 표시됩니다.|  
|`#`|이것이 `o`, `x`, 또는 `X` 형식과 함께 사용될 때, `#` 플래그는 출력값에 0이아닌 접두사로써 0, 0x, 또는 0X을 사용합니다.|공백 없이 표시됩니다.|  
||이것은 `e`, `E`, `f`, `a` 또는 `A` 형식과 함께 사용될 때 `#` 플래그는 소수점을 포함하는 출력값에 영향을 줍니다.|숫자 다음 이것이 오는 경우 소수점이 나타납니다.|  
||`g` 또는 `G` 형식과 함께 사용될 때, `#` 플래그는 소수점을 포함하는 출력값에 영향을 주고 끝에 오는 0의 잘림을 방지합니다.<br /><br /> `c`, `d`, `i`, `u`, 또는 `s` 과 함께 사용될 때 무시됩니다.|숫자 다음 이것이 오는 경우 소수점이 나타납니다.  끝에 오는 0이 잘립니다.|  
  
## 참고 항목  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)   
 [크기 사양](../c-runtime-library/size-specification.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)