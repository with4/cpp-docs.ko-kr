---
title: "printf 형식 필드 문자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf 함수, 형식 사양 필드"
  - "printf 함수, 형식 필드 문자"
ms.assetid: 699cb438-cd14-402e-9f81-c7a32acc3317
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# printf 형식 필드 문자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 사양에서 `type` 문자는 해당 인수가 문자, 문자열, 포인터, 정수 또는 부동 소수점 숫자로 변환되는지 여부를 지정하는 변환 지정자입니다.  `type` 문자는 요구되는 유일한 형식 사양 필드이며 선택적 필드 뒤에 표시됩니다.  
  
 형식 문자열 뒤에 나오는 인수는 해당 `type` 문자 및 선택적인 [크기](../c-runtime-library/size-specification.md) 접두사에 따라 해석됩니다.  문자 형식 `char` 및 `wchar_t`에 대한 변환은 `c` 또는 `C`를 사용하여 지정되고, 단일 바이트\/멀티바이트 또는 와이드 문자열은 사용 중인 형식 지정 함수에 따라 `s` 또는 `S`를 사용하여 지정됩니다.  `c` 및 `s`를 사용하여 지정된 문자 및 문자열 인수는 `printf` 패밀리 함수에서는 `char` 및 `char*`로 해석되고 `wprintf` 패밀리 함수에서는 `wchar_t` 및 `wchar_t*`로 해석됩니다.  `C` 및 `S`를 사용하여 지정된 문자 및 문자열 인수는 `printf` 패밀리 함수에서는 `wchar_t` 및 `wchar_t*`로 해석되고 `wprintf` 패밀리 함수에서는 `char` 및 `char*`로 해석됩니다.  
  
 `short`, `int`, `long`, `long long` 등의 정수 형식 및 그 `unsigned` 변형은 `d`, `i`, `o`, `u`, `x` 및 `X`를 사용하여 지정됩니다.  `float`, `double`, `long double` 등의 부동 소수점 형식은 `a`, `A`, `e`, `E`, `f`, `g` 및 `G`를 사용하여 지정됩니다.  `size` 필드 길이 접두사에 의해 수정되지 않는 한, 기본적으로 정수 인수는 `int` 형식으로 강제 변환되고 부동 소수점 인수는 `double`로 강제 변환됩니다.  64비트 시스템에서, `int`는 32비트 값이므로 `ll` 또는 `I64`의 `size` 접두사가 사용되지 않는 경우 64비트 정수는 출력을 위해 형식이 지정될 때 잘립니다.  `p`로 지정되는 포인터 형식은 플랫폼에 대해 기본 길이를 사용합니다.  
  
> [!NOTE]
>  `C`, `S`, `Z` 형식 문자와 `printf` 및 `wprintf` 함수와 함께 사용될 때 `c`, `s` 형식 문자의 동작은 Microsoft 확장이며 ANSI와 호환되지 않습니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서는 `F` 형식 문자를 지원하지 않습니다.  
  
### printf 형식 필드 문자  
  
|형식 문자|인수|출력 형식|  
|-----------|--------|-----------|  
|`c`|문자|`printf` 함수와 함께 사용될 때 단일 바이트 문자를 지정하고, `wprintf` 함수와 함께 사용될 때 와이드 문자를 지정합니다.|  
|`C`|문자|`printf` 함수와 함께 사용될 때 와이드 문자를 지정하고, `wprintf` 함수와 함께 사용될 때 단일 바이트 문자를 지정합니다.|  
|`d`|정수|부호 있는 10진수 정수입니다.|  
|`i`|정수|부호 있는 10진수 정수입니다.|  
|`o`|정수|부호 없는 8진수 정수입니다.|  
|`u`|정수|부호 없는 10진수 정수입니다.|  
|`x`|정수|부호 없는 16진수 정수이며 "abcdef"를 사용합니다.|  
|`X`|정수|부호 없는 16진수 정수이며 "ABCDEF"를 사용합니다.|  
|`e`|부동 소수점|부호 있는 값으로서 형식은 \[ – \]`d`**.**`dddd` e \[*부호*\]`dd[d]`입니다. 여기서 `d`는 하나의 10진수이고 `dddd`는 하나 이상의 10진수이며 `dd[d]`는 [출력 형식](../c-runtime-library/set-output-format.md) 및 지수 크기에 따라 두 개 또는 세 개의 10진수이고 *부호*는 \+ 또는 –입니다.|  
|`E`|부동 소수점|**e**가 아니라 **E**가 지수를 도입한다는 점을 제외하고는 `e` 형식과 동일합니다.|  
|`f`|부동 소수점|부호 있는 값으로서 형식은 \[ – \]`dddd`**.**`dddd`입니다. 여기서 `dddd`는 하나 이상의 10진수입니다.  소수점 앞의 자릿수는 수의 크기에 따라 다르며, 소수점 뒤의 자릿수는 요청된 정밀도에 따라 다릅니다.|  
|`g`|부동 소수점|`f` 또는 `e` 형식으로 표시되는 부호 있는 값으로서, 두 형식 중 주어진 값 및 정밀도에 대해 더 간단한 형식이 사용됩니다.  `e` 형식은 값의 지수가 –4보다 작거나 `precision` 인수보다 크거나 같을 때만 사용됩니다.  뒤에 나오는 0은 잘리고, 소수점은 뒤에 하나 이상의 수가 나오는 경우에만 나타납니다.|  
|`G`|부동 소수점|**e**가 아니라 **E**가 지수를 도입\(해당하는 경우\)한다는 점을 제외하고는 `g` 형식과 동일합니다.|  
|`a`|부동 소수점|부호 있는 16진수 배정밀도 부동 소수점 값으로서 형식은 \[−\]0x*h.hhhh* **p±**`dd`입니다. 여기서 *h.hhhh*는 가수의 16진수\(소문자 사용\)이고, `dd`는 지수에 사용되는 하나 이상의 숫자입니다.  정밀도는 소수점 뒤의 자릿수를 지정합니다.|  
|`A`|부동 소수점|부호 있는 16진수 배정밀도 부동 소수점 값으로서 형식은 \[−\]0X*h.hhhh* **P±**`dd`입니다. 여기서 *h.hhhh*는 가수의 16진수\(대문자 사용\)이고, `dd`는 지수에 사용되는 하나 이상의 숫자입니다.  정밀도는 소수점 뒤의 자릿수를 지정합니다.|  
|`n`|정수 포인터|지금까지 성공적으로 스트림 또는 버퍼에 쓴 문자의 수입니다.  이 값은 주소가 인수로 지정된 정수에 저장됩니다.  이 항목 뒷부분에 나오는 보안 정보를 참조하세요.|  
|`p`|포인터 유형|인수를 16진수로 된 주소로 표시합니다.|  
|`s`|문자열|`printf` 함수와 함께 사용될 때 단일 바이트 또는 멀티바이트 문자열을 지정하고, `wprintf` 함수와 함께 사용될 때는 와이드 문자열을 지정합니다.  첫 번째 null 문자 직전까지 또는 `precision` 값에 도달할 때까지 문자가 표시됩니다.|  
|`S`|문자열|`printf` 함수와 함께 사용될 때 와이드 문자열을 지정하고, `wprintf` 함수와 함께 사용될 때는 단일 바이트 또는 멀티바이트 문자열을 지정합니다.  첫 번째 null 문자 직전까지 또는 `precision` 값에 도달할 때까지 문자가 표시됩니다.|  
|`Z`|`ANSI_STRING` 또는 `UNICODE_STRING` 구조체|[ANSI\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) 또는 [UNICODE\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) 구조체의 주소가 인수로 전달되면 구조체의 `Buffer` 필드가 가리키는 버퍼에 포함된 문자열을 표시합니다.  길이 한정자 접두사 `w`를 사용하여 `UNICODE_STRING` 인수를 지정합니다\(예: `%wZ`\).  구조체의 `Length` 필드를 문자열의 길이\(바이트 단위\)로 설정해야 합니다.  구조체의 `MaximumLength` 필드를 버퍼의 길이\(바이트 단위\)로 설정해야 합니다.<br /><br /> 일반적으로 `Z` 형식 문자는 `dbgPrint` 및 `kdPrint` 등의 형식 사양을 사용하는 드라이버 디버깅 함수에서만 사용됩니다.|  
  
 부동 소수점 변환 지정자에 해당하는 인수가 제한 없음, 무한 또는 NAN인 경우 서식 있는 출력은 다음 표와 같습니다.  
  
|값|출력|  
|-------|--------|  
|\+ 무한대|`1.#INF` *random\-digits*|  
|– 무한대|`–1.#INF` *random\-digits*|  
|무한\(자동 NaN과 같음\)|*digit* `.#IND` *random\-digits*|  
|NAN|*digit* `.#NAN` *random\-digits*|  
  
> [!NOTE]
>  `%Z`에 해당하는 인수나 `%s` 또는 `%S`에 해당하는 인수의 `Buffer` 필드가 null 포인터인 경우 "\(null\)"이 표시됩니다.  
  
> [!NOTE]
>  모든 지수 형식에서 표시할 지수의 자릿수는 기본적으로 3입니다.  [\_set\_output\_format](../c-runtime-library/set-output-format.md) 함수를 사용하면 표시되는 자릿수를 2로 지정하지만 지수 크기로 인해 요구되는 경우에는 3으로 확장되도록 설정할 수 있습니다.  
  
> [!IMPORTANT]
>  `%n` 형식은 본질적으로 안전하지 않기 때문에 기본적으로 사용되지 않습니다.  형식 문자열에서 `%n`이 발견되는 경우 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기가 호출됩니다.  `%n` 지원을 사용하도록 설정하려면 [\_set\_printf\_count\_output](../c-runtime-library/reference/set-printf-count-output.md)을 참조하세요.  
  
## 참고 항목  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [플래그 지시문](../c-runtime-library/flag-directives.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)   
 [크기 사양](../c-runtime-library/size-specification.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)