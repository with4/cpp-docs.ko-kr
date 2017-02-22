---
title: "데이터 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.conversions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 변환"
  - "데이터 변환 루틴[C++]"
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 데이터 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 루틴은 한 폼에서 다른 폼으로 데이터를 변환합니다.  일반적으로 이러한 루틴은 작성할 변환 보다 더 빨리 실행 됩니다.  `to` 접두사로 시작하는 각 루틴은 함수 및 매크로 함수로 구현 됩니다.  다음 [함수와 매크로 사이에서 선택](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) 을 구현을 선택하는 방법에 대한 정보를 위해 참조하십시오.  
  
### 데이터 변환 루틴  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|정수의 절대값을 찾기|[\<caps:sentence id\="tgt11" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|문자열을 `float`로 변환하기|[\<caps:sentence id\="tgt13" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|문자열을 `int`로 변환하기|[System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx),  [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|문자열을 `__int64`로 변환하기|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx),  [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|문자열을 `long`로 변환하기|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx),  [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|`double` 를 지정된 길이의 문자열로 변환하기|[\<caps:sentence id\="tgt22" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md), [\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|`double` 를 다음의 소수점의 지정된 숫자에 문자열로 변환|[\<caps:sentence id\="tgt25" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md), [\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|`double` 번호를 문자열로 변환;문자열을 버퍼에 저장|[\<caps:sentence id\="tgt28" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md), [\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|`int` 또는 `__int64` 를 문자열로 변환|[\<caps:sentence id\="tgt31" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[labs](../misc/labs-llabs.md)|`long` 정수의 절대값을 찾기|[\<caps:sentence id\="tgt34" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_ltoa, \_ltow](../c-runtime-library/reference/ltoa-ltow.md), [\_ltoa\_s, \_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|문자열을 `long`로 변환하기|[\<caps:sentence id\="tgt37" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_mbbtombc, \_mbbtombc\_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1\-바이트 멀티 바이트 문자를 2\-바이트 멀티 바이트 문자에 해당하게 변환|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|일본 산업 표준 \(JIS\) 문자를 Microsoft 일본 \(JMS\) 문자로 변환|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JMS 문자를 JIS로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mbctohira, \_mbctohira\_l, \_mbctokata, \_mbctokata\_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|멀티 바이트 문자 코드를 1 바이트 히라가나 코드로 변환|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mbctohira, \_mbctohira\_l, \_mbctokata, \_mbctokata\_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|멀티 바이트 문자 코드를 1 바이트 가타카나 코드로 변환|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mbctombb, \_mbctombb\_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2\-바이트 멀티 바이트 문자를 1\-바이트 멀티 바이트 문자에 해당하게 변환|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|멀티 바이트의 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|멀티 바이트 문자를 해당 와이드 문자로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|문자열을 `double`로 변환하기|[\<caps:sentence id\="tgt72" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|문자열을 `long` 정수로 변환하기.|[\<caps:sentence id\="tgt74" sentenceid\="e227c715eb07e76d963577b7a799c2bb" class\="tgtSentence"\>System::Convert::ToInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)|  
|[strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|문자열을 `unsigned long` 정수로 변환하기.|[\<caps:sentence id\="tgt76" sentenceid\="121858e0b5a36f51abe1c266ab6fba6a" class\="tgtSentence"\>System::Convert::ToUInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)|  
|[strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|지정된\-로캘 정보와 관련된 인쇄 폼으로 문자열 변환|[\<caps:sentence id\="tgt78" sentenceid\="f57d3343223d1337ec503c6d3e02bac0" class\="tgtSentence"\>System::IFormattable::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.iformattable.tostring.aspx)|  
|[toascii, \_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|문자를 아스키 코드로 변환합니다.||  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|문자를 테스트 하고 현재 대문자라면 소문자로 변환|[\<caps:sentence id\="tgt82" sentenceid\="531bb90548dfdc9e9adea31b19ef1cc1" class\="tgtSentence"\>System::Char::ToLower\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)|  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|문자를 소문자로 조건없이 변환합니다.|[\<caps:sentence id\="tgt84" sentenceid\="067c0d5e10b0facda111402483f5cd3a" class\="tgtSentence"\>System::String::ToLower\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|문자를 테스트 하고 현재 대문자라면 소문자로 변환|[\<caps:sentence id\="tgt87" sentenceid\="fb184167443ee6ce1ae71a9ab9b01edb" class\="tgtSentence"\>System::Char::ToUpper\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char.toupper.aspx)|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|문자를 대문자로 조건없이 변환합니다.|[\<caps:sentence id\="tgt89" sentenceid\="86a1b4a5abf74ef908414687bc4c78df" class\="tgtSentence"\>System::String::ToUpper\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.toupper.aspx)|  
|[\_ultoa, \_ultow](../c-runtime-library/reference/ultoa-ultow.md), [\_ultoa\_s, \_ultow\_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|`unsigned` `long` 을 문자열로 변환합니다.|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|해당 멀티 바이트 문자의 시퀀스로 와이드 문자의 시퀀스를 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|와이드 바이트 문자를 해당 멀티바이트 문자로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|와이드 문자열을 `double`로 변환합니다.|[System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx),  [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx),  [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx),  [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|와이드 문자열을 `int`로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|와이드 문자열을 `__int64`로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|와이드 문자열을 `long`로 변환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)