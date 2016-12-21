---
title: "Visual C++의 텍스트 및 문자열 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASCII 문자[C++]"
  - "문자 집합[C++]"
  - "문자 집합[C++], 문자 집합 정보"
  - "문자 집합[C++], 유럽어 이외의 언어"
  - "전역화[C++]"
  - "전역화[C++], 문자 집합"
  - "국가별 응용 프로그램[C++], 국가별 응용 프로그램 정보"
  - "일본어 문자[C++]"
  - "간지 문자 지원[C++]"
  - "로컬 문자 집합[C++]"
  - "지역화[C++]"
  - "지역화[C++], 문자 집합"
  - "MBCS[C++], 국가별 프로그래밍"
  - "여러 언어 지원[C++]"
  - "비 유럽 문자[C++]"
  - "이식성[C++]"
  - "이식성[C++], 문자 집합"
  - "프로그래밍[C++], 국가별"
  - "코드 변환[C++]"
  - "변환[C++], 문자 집합"
  - "유니코드[C++]"
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: 12
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Visual C++의 텍스트 및 문자열
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

국제 시장을 대상으로 응용 프로그램을 개발할 때에는 해당 국가의 문자 집합을 적절하게 표현하는 것이 중요합니다.  ASCII 문자 집합은 0x00 – 0x7F 범위에서 문자를 정의합니다.  주로 유럽의 문자 집합에서는 ASCII 문자 집합과 동일하게 0x00 – 0x7F 범위에서 문자를 정의할 뿐만 아니라 0x80 – 0xFF 범위의 확장 문자를 정의합니다.  따라서 ASCII 문자 집합은 물론 많은 유럽 언어의 문자 집합을 표현하는 데에는 8비트의 SBCS\(싱글바이트 문자 집합\)만으로도 충분합니다.  그러나 한국어와 같은 일부 비 유럽 문자 집합에는 싱글바이트 코드 구성표로 표현할 수 있는 것보다 많은 문자가 있기 때문에 MBCS\(멀티바이트 문자 집합\) 인코딩이 필요합니다.  
  
## 단원 내용  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)  
 유니코드 및 MBCS 프로그래밍에 대한 Visual C\+\+ 지원을 설명합니다.  
  
 [유니코드 지원](../text/support-for-unicode.md)  
 싱글바이트로 표현할 수 없는 문자 집합을 포함하여 모든 문자 집합을 지원하기 위한 사양인 유니코드에 대해 설명합니다.  
  
 [MBCS 지원](../text/support-for-multibyte-character-sets-mbcss.md)  
 일본어 및 중국어와 같이 싱글바이트로 표현할 수 없는 문자 집합을 지원하기 위해 유니코드 대신 사용하는 MBCS\(멀티바이트 문자 집합\)에 대해 설명합니다.  
  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)  
 많은 데이터 형식, 루틴 및 기타 개체에 대한 Microsoft 관련 제네릭 텍스트 매핑을 제공합니다.  
  
 [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)  
 다양한 Visual C\+\+ 문자열 형식을 다른 문자열로 변환하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [국제화](../c-runtime-library/internationalization.md)  
 C 런타임 라이브러리의 국가별 지원에 대해 설명합니다.  
  
 [국가별 샘플](http://msdn.microsoft.com/ko-kr/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Visual C\+\+에서 국제화를 보여주는 샘플에 대한 링크를 제공합니다.  
  
 [언어 및 국가\/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 C 런타임 라이브러리의 언어 및 국가\/지역 문자열을 제공합니다.