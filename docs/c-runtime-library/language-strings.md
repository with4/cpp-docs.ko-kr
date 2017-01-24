---
title: "언어 문자열 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.strings"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "언어 문자열"
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 언어 문자열
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`setlocale` 및 `_create_locale` 함수는 유니코드 코드 페이지를 사용하지 않는 운영 체제에서 Windows NLS API를 지원하는 언어를 사용할 수 있습니다.  운영 체제 버전에서 지원 되는 언어 목록을 참조 하십시오. [국가별 언어 지원 \(NLS\) API 참조](http://msdn.microsoft.com/goglobal/bb896001.aspx).  언어 문자열은 **언어** 및 지원되는 언어의 열의 **언어 이름 약어** 의 값 중 하나가 될 수 있습니다.  C 런타임 라이브러리 구현도 이러한 언어 문자열을 지원합니다.  
  
|언어 문자열|해당 로캘 이름|  
|------------|--------------|  
|american|en\-US|  
|american english|en\-US|  
|american\-english|en\-US|  
|australian|en\-AU|  
|belgian|nl\-BE|  
|canadian|en\-CA|  
|chh|zh\-HK|  
|chi|zh\-SG|  
|chinese|zh|  
|chinese\-hongkong|zh\-HK|  
|chinese\-simplified|zh\-CN|  
|chinese\-singapore|zh\-SG|  
|chinese\-traditional|zh\-TW|  
|dutch\-belgian|nl\-BE|  
|english\-american|en\-US|  
|english\-aus|en\-AU|  
|english\-belize|en\-BZ|  
|english\-can|en\-CA|  
|english\-caribbean|en\-029|  
|english\-ire|en\-IE|  
|english\-jamaica|en\-JM|  
|english\-nz|en\-NZ|  
|english\-south africa|en\-ZA|  
|english\-trinidad y tobago|en\-TT|  
|english\-uk|en\-GB|  
|english\-us|en\-US|  
|english\-usa|en\-US|  
|french\-belgian|fr\-BE|  
|french\-canadian|fr\-CA|  
|french\-luxembourg|fr\-LU|  
|french\-swiss|fr\-CH|  
|german\-austrian|de\-AT|  
|german\-lichtenstein|de\-LI|  
|german\-luxembourg|de\-LU|  
|german\-swiss|de\-CH|  
|irish\-english|en\-IE|  
|italian\-swiss|it\-CH|  
|norwegian|no|  
|norwegian\-bokmal|nb\-NO|  
|norwegian\-nynorsk|nn\-NO|  
|portuguese\-brazilian|pt\-BR|  
|spanish\-argentina|es\-AR|  
|spanish\-bolivia|es\-BO|  
|spanish\-chile|es\-CL|  
|spanish\-colombia|es\-CO|  
|spanish\-costa rica|es\-CR|  
|spanish\-dominican republic|es\-DO|  
|spanish\-ecuador|es\-EC|  
|spanish\-el salvador|es\-SV|  
|spanish\-guatemala|es\-GT|  
|spanish\-honduras|es\-HN|  
|spanish\-mexican|es\-MX|  
|spanish\-modern|es\-ES|  
|spanish\-nicaragua|es\-NI|  
|spanish\-panama|es\-PA|  
|spanish\-paraguay|es\-PY|  
|spanish\-peru|es\-PE|  
|spanish\-puerto rico|es\-PR|  
|spanish\-uruguay|es\-UY|  
|spanish\-venezuela|es\-VE|  
|swedish\-finland|sv\-FI|  
|swiss|de\-CH|  
|uk|en\-GB|  
|us|en\-US|  
|usa|en\-US|  
  
## 참고 항목  
 [로캘 이름, 언어 및 국가\/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [국가\/지역 문자열](../c-runtime-library/country-region-strings.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)