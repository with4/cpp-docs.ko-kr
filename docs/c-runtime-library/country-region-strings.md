---
title: 국가-지역 문자열 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f227feec25e3b487772f8e469651f08be825419f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605632"
---
# <a name="countryregion-strings"></a>Country/Region Strings

국가 및 지역 문자열을 언어 문자열과 결합하여 `setlocale`, `_wsetlocale`, `_create_locale`및 `_wcreate_locale` 함수에 대한 로캘 사양을 만들 수 있습니다. 다양한 Windows 운영 체제 버전에서 지원하는 국가 및 지역 이름 목록은 [MS-LCID]: Windows LCID(언어 코드 식별자) 참조에서 [Appendix A: Product Behavior](https://msdn.microsoft.com/library/cc233982.aspx)(부록 A: 제품 동작)의 표에 있는 **언어**, **위치** 및 **언어 태그** 열을 참조하세요. 사용 가능한 로캘 이름 및 관련 값을 열거하는 코드 예제는 [NLS: 이름 기반 API 샘플](/windows/desktop/intl/nls--name-based-apis-sample)을 참조하세요.

## <a name="additional-supported-country-and-region-strings"></a>지원되는 추가 국가 및 지역 문자열

또한 Microsoft C 런타임 라이브러리 구현은 다음과 같은 국가/지역 문자열과 약어를 추가로 지원합니다.

|국가/지역 문자열|약어|해당 로캘 이름|
|----------------------------|------------------|----------------------------|
|america|USA|ko-KR|
|britain|GBR|en-GB|
|china|CHN|zh-CN|
|czech|CZE|cs-CZ|
|england|GBR|en-GB|
|great britain|GBR|en-GB|
|holland|NLD|nl-NL|
|hong-kong|HKG|zh-HK|
|new-zealand|NZL|en-NZ|
|nz|NZL|en-NZ|
|pr china|CHN|zh-CN|
|pr-china|CHN|zh-CN|
|puerto-rico|PRI|es-PR|
|slovak|SVK|sk-SK|
|south africa|ZAF|af-ZA|
|south korea|KOR|ko-KR|
|south-africa|ZAF|af-ZA|
|south-korea|KOR|ko-KR|
|trinidad & tobago|TTO|en-TT|
|uk|GBR|en-GB|
|united-kingdom|GBR|en-GB|
|united-states|USA|ko-KR|
|us|USA|ko-KR|

## <a name="see-also"></a>참고 항목

[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
[언어 문자열](../c-runtime-library/language-strings.md)  
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)  
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)  
