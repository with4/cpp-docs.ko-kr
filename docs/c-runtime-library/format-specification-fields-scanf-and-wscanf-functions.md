---
title: "형식 사양 필드: scanf 및 wscanf 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wscanf"
  - "scanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "너비, scanf 함수의 사양"
  - "scanf 형식 사양"
  - "scanf 너비 사양"
  - "scanf 형식 필드 문자"
  - "형식 필드, scanf 함수"
  - "scanf 함수의 형식 사양 필드"
  - "형식 필드"
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 형식 사양 필드: scanf 및 wscanf 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 정보는 보안버전을 포함한 `scanf` 함수군 전체에 적용됩니다. 또한 `scanf`에 대한 `stdin`와 같은 `scanf` 함수가 입력된 스트림을 어떻게 구문을 분석 하여 프로그램 변수에 삽입되는지에 대해 말할 때 사용되는 심벌을 설명합니다.  
  
 형식 사양은 다음의 폼을 갖습니다.  
  
 `%` `*`\] [width](../c-runtime-library/scanf-width-specification.md) \[{[h &#124; l &#124; ll &#124; I64 &#124; L](../c-runtime-library/scanf-width-specification.md)}\][type](../c-runtime-library/scanf-type-field-characters.md)  
  
 `format` 인수는 입력에 대한 해석을 지정하고 다음 중 하나 이상을 포함할 수 있습니다.  
  
-   공백: 공백 \(' '\). 탭 \('\\t'\). 또는 줄 바꿈 \('\\n'  공백 문자는 `scanf`를 통해 읽을 수 있지만 다음 공백이 아닌 문자까지 입력되는 연속적인 공백 문자들은 저장되지 않습니다.  형식내의 하나의 공백 문자는 모든 숫자 \(0 포함\) 및 공백 문자가 조합된 입력과 연결됩니다.  
  
-   백분율 기호 \(`%`\)를 제외한 공백이 아닌 문자.  공백이 아닌 문자는 연결되는 공백이 아닌 문자를 `scanf`를 통해 읽을 수 있지만 저장하지는 않습니다.  입력 스트림의 다음 문자가 일치 하지 않는 경우 `scanf`를 종료 합니다.  
  
-   백분율 기호 \(`%`\)로 나타나는 서식 설정.  서식 설정은 입력된 문자를 `scanf`를 통해 읽고 지정된 형식의 값으로 변환 합니다.  값은 인수 목록 가운데 하나에 할당 됩니다.  
  
 서식은 왼쪽에서 오른쪽으로 읽습니다.  서식 설정 외부의 문자들은 입력된 스트림의 문자 순서와 일치할 것으로 예상 됩니다. 입력 스트림의 일치 하는 문자는 검색 되지만 저장 되지는 않습니다.  입력 스트림의 문자가 서식 설정과 충돌할 경우, `scanf`는 종료되고 입력 스트림안의 문자는 읽히지 않은채로 남습니다.  
  
 첫 번째 서식 설정을 접할 때, 입력된 첫번째 필드의 값이 사양에 따라 변환 되어 첫 번째 `argument`에 의해 지정 된 위치에 저장됩니다.  두 번째 서식 설정은 두 번째에 입력된 필드를 변환하여 두 번째 `argument`에 저장하고 이러한 형식 문자열의 끝까지 이어집니다.  
  
 입력 필드는 첫 번째 공백 문자 \(공백, 탭 또는 줄 바꿈\) 까지 또는 서식 설정에 의해 변환될 수 없는 첫 문자, 필드 너비\(지정 된 경우\)에 해당하는 모든 문자로 정의됩니다.  주어진 설정에 너무 많은 인수가 있을 경우 추가적인 인수들은 평가되지만 무시됩니다.  모든 서식 설정에 충분한 인수가 없는 경우 결과를 예측할 수 없습니다.  
  
 서식 설정의 각 필드는 설정 단일 문자 또는 특정 서식 옵션을 나타내는 숫자입니다.  마지막 선택적 형식 필드 뒤에 나타나는 `type` 문자는 입력 필드가 문자, 문자열 또는 숫자 가운데 어떤 것으로 해석 될지를 결정합니다.  
  
 가장 간단한 서식 설정은 백분율 기호와 `type` 문자만을 포함합니다. \(예를 들어, `%s`\).  백분율 기호 \(`%`\)뒤에 아무런 의미가 없는 서식 제어 문자가 따를 경우, 해당 문자 및 이후의 문자들 \(다음 백분율 기호까지\)은 입력과 반드시 일치하는 일반적인 문자의 시퀀스로 취급합니다.  예를 들어, 백분율 기호 문자를 입력으로 지정 하려면  `%%` 를 사용합니다.  
  
 백분율 기호 다음에 나타나는 별표 \(`*`\)는 지정된 형식으로 해석 되는 다음 입력 필드를 표시 하지 않습니다.  필드는 검색 되지만 저장 되지 않습니다.  
  
 `scanf`함수군의 보안 버전\(`_s`를 접미사로 하는\)은 다음의 각 형식 매개 변수에 전달될 버퍼 크기를 필요로 합니다. `c`, `C`, `s`, `S`, `[`.  `scanf`함수군의 보안 버전에 대한 보다 더 많은 정보는 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)를 참조하시기 바랍니다.  
  
## 참고 항목  
 [scanf 너비 사양](../c-runtime-library/scanf-width-specification.md)   
 [scanf 형식 필드 문자](../c-runtime-library/scanf-type-field-characters.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)