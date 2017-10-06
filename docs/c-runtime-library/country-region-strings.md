---
title: "국가-지역 문자열 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 22da7776e46171467a37d46c3de3227f060eaf77
ms.openlocfilehash: 272ce38cee55661a3f4a1eb751c8808b355b59be
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
# <a name="countryregion-strings"></a>Country/Region Strings
국가 및 지역 문자열을 언어 문자열과 결합하여 `setlocale`, `_wsetlocale`, `_create_locale`및 `_wcreate_locale` 함수에 대한 로캘 사양을 만들 수 있습니다. 다양한 Windows 운영 체제 버전에서 지원되는 국가/지역 이름 목록은 [NLS(국가별 언어 지원) API 참조(영문)](https://www.microsoft.com/resources/msdn/goglobal/default.mspx)를 참조하세요. 목록에서 국가/지역 문자열은 **로캘 - 국가/지역별 언어** 열의 국가 값 또는 **국가 또는 지역별 이름 약어**의 약어 중 하나일 수 있습니다. 버전별 Windows 운영 체제의 언어 지원에 대한 자세한 내용은 [MS-LCID]: Windows LCID(언어 코드 식별자) 참조의 [부록 A: 제품 동작(영문)](http://msdn.microsoft.com/goglobal/bb896001.aspx)을 참조하세요.  
  
 또한 C 런타임 라이브러리 구현은 다음과 같은 국가/지역 문자열과 약어를 추가로 지원합니다.  
  
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
