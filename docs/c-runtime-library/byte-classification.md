---
title: "바이트 분류 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types.bytes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "바이트 분류 루틴"
  - "바이트, 테스트"
  - "코드 페이지 932"
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 바이트 분류
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 루틴은 각 테스트 조건의 만족도에 대한 멀티 바이트 문자를 지정한 바이트입니다.  그렇지 않으면 지정된 경우를 제외하고 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  
  
> [!NOTE]
>  \(정의에 의해, 0와 127사이의 ASCII 문자는 모든 멀티바이트 문자 집합의 부분집합입니다.\)  예를 들어, 일본어의 가타카나 문자 집합은 ASCII가 아닌 문자 뿐 아니라 ASCII를 포함합니다.  
  
 다음 표에 있는 미리 정의된 상수는 CTYPE.H에 정의 되어 있습니다.  
  
### 멀티 바이트 문자 바이트 분류 루틴  
  
|루틴|바이트 테스트 조건|해당 .NET Framework|  
|--------|----------------|-----------------------|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|선행 바이트에 대해 테스트 결과는 현재 로캘의 `LC_CTYPE` 범주 설정에 따라 달라집니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbalnum, \_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum &#124;&#124; _ismbbkalnum`|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbalpha, \_ismbbalpha\_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|`isalpha &#124;&#124; _ismbbkalnum`|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbgraph, \_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|이 `_ismbbprint`와 같이, 그러나 `_ismbbgraph` 은 빈 공백 문자\(0x20\)를 포함하지 않습니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbkalnum, \_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Non\-ASCII 텍스트 기호 이외의 문장 부호입니다.  예를 들어, 코드 페이지 932 에서만, `_ismbbkalnum` 은 가타카나 영문자에 대한 테스트를 합니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbkana, \_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana \(0xA1 – 0xDF\), code page 932 only|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbkprint, \_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|비 ASCII 텍스트 또는 ASCII가 아닌 문장 기호입니다.  예를 들어, 코드 페이지 932 에서, `_ismbbkprint` 가타카나 영숫자 또는 가타카나 문장에 대해 테스트합니다\(범위: 0xA1 – 0xDF\).|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbkpunct, \_ismbbkpunct\_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Non\-ASCII 문장입니다.  예를 들어, 코드 페이지 932 에서만, `_ismbbkpunct` 은 가타카나 구두점에 대한 테스트를 합니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbblead, \_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|멀티 바이트 문자의 첫 번째 바이트입니다.  코드에서 페이지 932, 유효 범위는 0x81\-0x9F 0xE0 – 0xFC.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbprint, \_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint &#124;&#124; _ismbbkprint. ismbbprint` 는 공백 문자 \(0x20\)를 포함합니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbpunct, \_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct &#124;&#124; _ismbbkpunct`|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|멀티 바이트 문자의 두 번째 바이트입니다.  코드에서 페이지 932, 유효 범위는 0x40\-0x7E, 0x80 – 0xEC.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_ismbslead, \_ismbslead\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|선행 바이트 \(문자열 컨텍스트에서\)|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[ismbstrail, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|후행 바이트 \(문자열 컨텍스트에서\)|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_mbbtype, \_mbbtype\_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|이전 바이트 기반의 반환 바이트 형식입니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[\_mbsbtype, \_mbsbtype\_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|문자열 내에서 바이트의 반환 형식입니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|멀티 바이트 문자 변환의 상태를 추적합니다.|적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.|  
  
 LIMITS.H 에 정의 된 `MB_LEN_MAX` 는 모든 멀티 바이트 문자를 포함할 수 있는 바이트의 최대 길이를 확장합니다.  STDLIB.H에 정의된 `MB_CUR_MAX` 는 현재 로캘에서 멀티 바이트 문자의 최대 길이\(바이트\)를 확장합니다.  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)