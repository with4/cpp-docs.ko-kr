---
title: 언어 문자열 | Microsoft Docs
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
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eaab56876651a1056ef89d57bebb2799d1bb3194
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604143"
---
# <a name="language-strings"></a>Language Strings

[setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 및 [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) 함수는 유니코드 코드 페이지를 사용하지 않는 운영 체제에서 Windows NLS API를 지원하는 언어를 사용할 수 있습니다. 운영 체제 버전별 지원되는 언어 목록은 [MS-LCID]: Windows LCID(언어 코드 식별자) 참조의 [Appendix A: Product Behavior](https://msdn.microsoft.com/library/cc233982.aspx)(부록 A: 제품 동작)를 참조하세요. 언어 문자열은 지원되는 언어 목록의 **언어** 및 **언어 태그** 열에 있는 임의의 값일 수 있습니다. 사용 가능한 로캘 이름 및 관련 값을 열거하는 코드 예제는 [NLS: 이름 기반 API 샘플](/windows/desktop/intl/nls--name-based-apis-sample)을 참조하세요.

## <a name="additional-supported-language-strings"></a>지원되는 추가 언어 문자열

Microsoft C 런타임 라이브러리 구현은 다음 언어 문자열도 지원합니다.

|언어 문자열|해당 로캘 이름|
|---------------------|----------------------------|
|american|ko-KR|
|american english|ko-KR|
|american-english|ko-KR|
|australian|en-AU|
|belgian|nl-BE|
|canadian|en-CA|
|chh|zh-HK|
|chi|zh-SG|
|chinese|zh|
|chinese-hongkong|zh-HK|
|chinese-simplified|zh-CN|
|chinese-singapore|zh-SG|
|chinese-traditional|zh-TW|
|dutch-belgian|nl-BE|
|english-american|ko-KR|
|english-aus|en-AU|
|english-belize|en-BZ|
|english-can|en-CA|
|english-caribbean|en-029|
|english-ire|en-IE|
|english-jamaica|en-JM|
|english-nz|en-NZ|
|english-south africa|en-ZA|
|english-trinidad y tobago|en-TT|
|english-uk|en-GB|
|english-us|ko-KR|
|english-usa|ko-KR|
|french-belgian|fr-BE|
|french-canadian|fr-CA|
|french-luxembourg|fr-LU|
|french-swiss|fr-CH|
|german-austrian|de-AT|
|german-lichtenstein|de-LI|
|german-luxembourg|de-LU|
|german-swiss|de-CH|
|irish-english|en-IE|
|italian-swiss|it-CH|
|norwegian|no|
|norwegian-bokmal|nb-NO|
|norwegian-nynorsk|nn-NO|
|portuguese-brazilian|pt-BR|
|spanish-argentina|es-AR|
|spanish-bolivia|es-BO|
|spanish-chile|es-CL|
|spanish-colombia|es-CO|
|spanish-costa rica|es-CR|
|spanish-dominican republic|es-DO|
|spanish-ecuador|es-EC|
|spanish-el salvador|es-SV|
|spanish-guatemala|es-GT|
|spanish-honduras|es-HN|
|spanish-mexican|es-MX|
|spanish-modern|es-ES|
|spanish-nicaragua|es-NI|
|spanish-panama|es-PA|
|spanish-paraguay|es-PY|
|spanish-peru|es-PE|
|spanish-puerto rico|es-PR|
|spanish-uruguay|es-UY|
|spanish-venezuela|es-VE|
|swedish-finland|sv-FI|
|swiss|de-CH|
|uk|en-GB|
|us|ko-KR|
|usa|ko-KR|

## <a name="see-also"></a>참고 항목

[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
[국가/지역 문자열](../c-runtime-library/country-region-strings.md)  
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)  
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)  
