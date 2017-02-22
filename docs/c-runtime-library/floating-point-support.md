---
title: "부동 소수점 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "부동 소수점 숫자"
  - "부동 소수점 숫자, 수학 루틴"
  - "수학 루틴"
ms.assetid: e4fcaf69-5c8e-4854-a9bb-1f412042131e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 부동 소수점 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

여러 Microsoft 런타임 라이브러리 함수를 사용하려면 Math Coprocessor 또는 컴파일러와 함께 제공되는 부동 소수점 라이브러리의 부동 소수점 지원이 필요합니다.  부동 소수점 지원 함수는 필요한 경우에만 로드합니다.  
  
 `printf` 또는 `scanf` 패밀리에서 함수 호출의 서식 문자열에 부동 소수점 형식 지정자를 사용하면 인수 목록에서 부동 소수점 값 또는 부동 소수점 값에 대한 포인터를 지정하여 컴파일러에 부동 소수점 지원이 필요함을 알려야 합니다.  
  
 부동 소수점 예외를 처리하는 방법을 보여주는 샘플 코드는 [\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)를 참조하세요.  
  
 중간 값의 부동 소수점 정밀도는 [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) 함수가 제어합니다.  기본적으로 `_controlfp`의 정밀도 컨트롤은 53비트\(\_PC\_53\)로 설정되어 있습니다.  FP10.OBJ를 사용하여 연결하면 기본 정밀도 컨트롤이 64비트\(\_PC\_64\)로 변경됩니다.  링커 명령줄에서 FP10.OBJ는 LIBC.LIB, LIBCMT.LIB 또는 MSVCRT.LIB 앞에 와야 합니다.  
  
### 부동 소수점 함수  
  
|루틴|기능|.NET Framework의 해당 값|  
|--------|--------|--------------------------|  
|[abs](../Topic/abs.md)|`int`의 절대값 반환|[\<caps:sentence id\="tgt14" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[acos, acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|아크코사인 계산|[\<caps:sentence id\="tgt17" sentenceid\="954a441495360a1fa8b0170297b2ff38" class\="tgtSentence"\>System::Math::Acos\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)|  
|[asin, asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|아크사인 계산|[\<caps:sentence id\="tgt20" sentenceid\="313917cde9698a0924536719f5bece25" class\="tgtSentence"\>System::Math::Asin\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)|  
|[atan, atanf, atan2, atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|아크탄젠트 계산|[System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx), [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|문자열을 배정밀도 부동 소수점 값으로 변환|[System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx), [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[Bessel 함수](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|Bessel 함수 `_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn` 계산|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.|  
|[\_cabs](../c-runtime-library/reference/cabs.md)|복소수의 절대값 찾기|해당 사항 없음.|  
|[cbrt](../c-runtime-library/reference/cbrt-cbrtf-cbrtl.md)|세제곱근 계산|해당 사항 없음.|  
|[ceil, ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|정수 한계 찾기|[\<caps:sentence id\="tgt39" sentenceid\="656009d71fb974368bded363746de018" class\="tgtSentence"\>System::Math::Ceiling\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|배정밀도 부동 소수점 또는 long 배정밀도 부동 소수점 인수의 부호 반전|해당 사항 없음.|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|부동 소수점 상태 단어 가져오기 및 지우기|해당 사항 없음.|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md), [\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|이전 부동 소수점 제어 단어 가져오기 및 새 제어 단어 값 설정|해당 사항 없음.|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|부호가 다른 값 반환|해당 사항 없음.|  
|[cos, cosf, cosh, coshf](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|코사인 계산|[System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx), [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)|  
|[difftime](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|지정된 두 시간 값 간의 차이 계산|[\<caps:sentence id\="tgt54" sentenceid\="5f4f365a3cd7f368db2f6ce31b797fdf" class\="tgtSentence"\>System::DateTime::Subtract\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[div](../c-runtime-library/reference/div.md)|정수를 다른 정수로 나눠 몫과 나머지 반환|해당 사항 없음.|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md), [\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|`double`을 지정된 길이의 문자열로 변환|[\<caps:sentence id\="tgt60" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[exp, expf](../c-runtime-library/reference/exp-expf.md)|지수 함수 계산|[\<caps:sentence id\="tgt63" sentenceid\="81a65df6ac66cdc4a4b12c2f7e555487" class\="tgtSentence"\>System::Math::Exp\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)|  
|[fabs, fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|절대값 찾기|[\<caps:sentence id\="tgt66" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md), [\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|`double`을 소수점 뒤의 자릿수를 지정하는 문자열로 변환|[\<caps:sentence id\="tgt69" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|지정된 배정밀도 부동 소수점 값이 유한인지 확인|[\<caps:sentence id\="tgt72" sentenceid\="8d081c50adeda3dde4cebab81a0b3583" class\="tgtSentence"\>System::Double::IsInfinity\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)|  
|[floor, floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|인수와 같거나 작은 가장 큰 정수 찾기|[\<caps:sentence id\="tgt75" sentenceid\="609db9ab0433b647d5350d3b965d70f9" class\="tgtSentence"\>System::Math::Floor\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)|  
|[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)|부동 소수점 나머지 찾기|[\<caps:sentence id\="tgt78" sentenceid\="127a04426267ccb17fb4b566ad56de9c" class\="tgtSentence"\>System::Math::IEEERemainder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)|  
|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|부동 소수점 클래스에 대한 정보가 포함된 상태 단어 반환|[System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx), [System::Double::IsNegativeInfinity](https://msdn.microsoft.com/en-us/library/system.double.isnegativeinfinity.aspx), [System::Double::IsPositiveInfinity](https://msdn.microsoft.com/en-us/library/system.double.ispositiveinfinity.aspx), [System::Double::IsNan](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|IEEE 부동 소수점 예외 처리를 위한 사용자 정의 트랩 처리기 호출|해당 사항 없음.|  
|[\_fpreset](../c-runtime-library/reference/fpreset.md)|부동 소수점 수학 패키지 다시 초기화||  
|[frexp](../c-runtime-library/reference/frexp.md)|지수 값 계산|해당 사항 없음.|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md), [\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|부동 소수점 값을 문자열로 전환|[\<caps:sentence id\="tgt92" sentenceid\="ed8e24ad5c647dc4efa4fbe1e9bbc5e3" class\="tgtSentence"\>System::Convert::ToString\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)|  
|[hypot, hypotf, hypotl, \_hypot, \_hypotf, \_hypotl](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|직각 삼각형의 빗변 계산|해당 사항 없음.|  
|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|NaN\(숫자가 아님\)에 대해 지정된 배정밀도 부동 소수점 값 확인|[\<caps:sentence id\="tgt97" sentenceid\="18f7dc07d0c506c23f2f7eb89262d274" class\="tgtSentence"\>System::Double::IsNan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.isnan.aspx)|  
|[labs](../misc/labs-llabs.md)|`long`의 절대값 반환|[\<caps:sentence id\="tgt100" sentenceid\="9594ba199e25e9de6b463c8efc9fbe95" class\="tgtSentence"\>System::Math::Abs\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)|  
|[ldexp](../c-runtime-library/reference/ldexp.md)|인수와 2<sup>exp</sup>\(지정된 거듭제곱\)의 곱 계산|[\<caps:sentence id\="tgt103" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[ldiv](../c-runtime-library/reference/ldiv-lldiv.md)|`long` 정수 하나를 다른 정수로 나눠 몫과 나머지 반환|해당 사항 없음.|  
|[log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|자연 로그 또는 base\-10 알고리즘 계산|[System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx), [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)|  
|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|배정밀도 부동 소수점 인수의 지수 값 추출|해당 사항 없음.|  
|[\_lrotl, \_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|`unsigned long int`를 왼쪽\(`_lrotl`\) 또는 오른쪽\(`_lrotr`\)으로 시프트|해당 사항 없음.|  
|[\_matherr](../c-runtime-library/reference/matherr.md)|수학 오류 처리|해당 사항 없음.|  
|[\_\_max](../c-runtime-library/reference/max.md)|두 값 중 큰 값 반환|[\<caps:sentence id\="tgt121" sentenceid\="6f9dcb228534c3e5b0013615b2b1d003" class\="tgtSentence"\>System::Math::Max\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)|  
|[\_\_min](../c-runtime-library/reference/min.md)|두 값 중 작은 값 반환|[\<caps:sentence id\="tgt124" sentenceid\="ff471983fc666dec7ba58b17a0bf76e6" class\="tgtSentence"\>System::Math::Min\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)|  
|[modf, modff](../c-runtime-library/reference/modf-modff-modfl.md)|인수를 정수와 소수 부분으로 나누기|해당 사항 없음.|  
|[nan, nanf, nanl](../c-runtime-library/reference/nan-nanf-nanl.md)|Quiet NaN 값 반환|[\<caps:sentence id\="tgt129" sentenceid\="c251043405ffa73fe857c83428b58fdc" class\="tgtSentence"\>System::Double::NaN\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)|  
|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|다음으로 표현 가능한 인접 수 반환|해당 사항 없음.|  
|[pow, powf](../c-runtime-library/reference/pow-powf-powl.md)|거듭제곱으로 제곱된 값 계산|[\<caps:sentence id\="tgt135" sentenceid\="839e85fe5fb98e8520d40a703d06932b" class\="tgtSentence"\>System::Math::Pow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|지정한 서식에 따라 `stdout`에 데이터 쓰기|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx), [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)|  
|[rand](../c-runtime-library/reference/rand.md), [rand\_s](../c-runtime-library/reference/rand-s.md)|의사 난수 가져오기|[\<caps:sentence id\="tgt141" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[rint, rintf, rintl](../c-runtime-library/reference/rint-rintf-rintl.md)|가장 가까운 정수로 반올림\(부동 소수점 형식\)|[\<caps:sentence id\="tgt143" sentenceid\="1c04aeb4aeff1752cb65adabcee29f53" class\="tgtSentence"\>System::Math::Round\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)|  
|[\_rotl, \_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|`unsigned int`를 왼쪽\(`_rotl`\) 또는 오른쪽\(`_rotr`\)으로 시프트|해당 사항 없음.|  
|[\_scalb](../c-runtime-library/reference/scalb.md)|2의 거듭제곱으로 인수 증가|해당 사항 없음.|  
|[scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl](../c-runtime-library/reference/scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl.md)|`FLT_RADIX`의 정수 거듭제곱으로 곱하기|해당 사항 없음.|  
|[scanf, wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|지정된 형식에 따라 `stdin`에서 데이터를 읽고 지정된 위치에 데이터 쓰기|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx), [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)|  
|[\_set\_controlfp](../c-runtime-library/reference/set-controlfp.md)|새 제어 단어 값 설정|해당 사항 없음.|  
|[sin, sinf, sinh, sinhf](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|사인 또는 쌍곡 사인 계산|[System::Math::Sin](https://msdn.microsoft.com/en-us/library/system.math.sin.aspx), [System::Math::Sinh](https://msdn.microsoft.com/en-us/library/system.math.sinh.aspx)|  
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|제곱근 찾기|[\<caps:sentence id\="tgt162" sentenceid\="1a91af0bd8c63b4be64c7a0bec8dc8c4" class\="tgtSentence"\>System::Math::Sqrt\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)|  
|[srand](../c-runtime-library/reference/srand.md)|의사 난수 계열 초기화|[\<caps:sentence id\="tgt165" sentenceid\="00574fde17be9de3e07567ef5abe0110" class\="tgtSentence"\>System::Random Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.random.aspx)|  
|[\_status87, \_statusfp, \_statusfp2](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|부동 소수점 상태 단어 가져오기|해당 사항 없음.|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|문자열을 배정밀도 값으로 변환|[\<caps:sentence id\="tgt169" sentenceid\="363f8f2cb09f8ca850491a65df66522e" class\="tgtSentence"\>System::Convert::ToDouble\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)|  
|[tan, tanf, tanh, tanhf](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|탄젠트 또는 쌍곡 탄젠트 계산|[System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx), [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)