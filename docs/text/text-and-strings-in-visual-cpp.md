---
title: "Visual c + +의 텍스트 및 문자열 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 1e302fb7003358a75cb0b3022c4264c1e63518e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++의 텍스트 및 문자열
국제 시장을 겨냥 한 응용 프로그램을 개발 하는 중요 한 요소에는 로컬 문자 집합의 적절 한 표현입니다. ASCII 문자 집합 0x00-0x7F 범위의 문자를 정의합니다. 주로 유럽 0x00-0x7F 범위 내 문자를 동일 하 게 ASCII 문자 집합을 정의 하 고 또한 확장된 문자 0xff 0x80에서 집합을 정의 하는 다른 문자 집합입니다. 따라서 (SBCS)는 8 비트, 단일 바이트 문자 집합은 ASCII 문자 집합은 물론 많은 유럽 언어에 대 한 문자 집합 표현 하기에 충분 합니다. 그러나 일본어 간지 같은 일부 비 유럽 문자 집합 싱글바이트 코드 구성표로 나타내고 수 때문에 멀티 바이트 문자 집합 (MBCS) 인코딩이 필요 보다 훨씬 더 많은 문자를 포함 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)  
 유니코드 및 MBCS 프로그래밍에 대 한 Visual c + + 지원에 설명 합니다.  
  
 [유니코드 지원](../text/support-for-unicode.md)  
 유니코드를 싱글바이트로 표현할 수 없는 문자 집합을 포함 하 여 모든 문자 집합을 지원 하기 위한 사양에 설명 합니다.  
  
 [멀티 바이트 문자 집합 (MBCS)에 대 한 지원](../text/support-for-multibyte-character-sets-mbcss.md)  
 일본어 및 중국어 싱글바이트로 표현할 수 없는 같이 문자 집합 지원에 대 한 유니코드 대신 MBCS를 설명 합니다.  
  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)  
 많은 데이터 형식, 루틴 및 다른 개체에 대 한 Microsoft 고유의 일반 텍스트 매핑을 제공합니다.  
  
 [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)  
 다양 한 Visual c + + 문자열 형식을 다른 문자열로 변환 하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 단원  
 [국제화](../c-runtime-library/internationalization.md)  
 C 런타임 라이브러리의 다국어 기능 지원에 설명 합니다.  
  
 [국가별 샘플](http://msdn.microsoft.com/en-us/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Visual c + +에서 국제화를 보여주는 샘플에 대 한 링크를 제공 합니다.  
  
 [언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 C 런타임 라이브러리의 언어 및 국가/지역 문자열을 제공합니다.