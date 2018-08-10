---
title: Visual c + +의 텍스트 및 문자열 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8eaf5425bab79d31391e6ccd82e03c667de1271c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016628"
---
# <a name="text-and-strings-in-visual-c"></a>Visual C++의 텍스트 및 문자열
국제 시장 용 응용 프로그램 개발의 중요 한 측면에는 로컬 문자 집합의 적합 한 표현입니다. ASCII 문자 집합 0x00-0x7F 범위의 문자를 정의합니다. 주로 유럽 ASCII 문자 집합과 동일 하 게 0x00-0x7F 범위의 문자를 정의 하 고 또한 0xFF 뿐만 아니라 0x80에서로 확장된 된 문자를 정의 하는 다른 문자 집합입니다. 따라서 (SBCS)는 8 비트, 단일 바이트 문자 집합은 ASCII 문자 집합 뿐만 아니라 많은 유럽 언어에 대 한 문자 집합을 나타내는 데 충분 합니다. 그러나 한국어와 같은 일부 비 유럽 문자 집합에는 싱글바이트 코딩 구성표로 나타낼 수 있습니다 및 멀티 바이트 문자 집합 (MBCS) 인코딩이 필요 것 보다 많은 문자가 포함 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)  
 유니코드 및 MBCS 프로그래밍을 위한 Visual c + + 지원을 설명합니다.  
  
 [유니코드 지원](../text/support-for-unicode.md)  
 유니코드를 싱글바이트로 표현할 수 없는 문자 집합을 포함 하 여 모든 문자 집합을 지원 하기 위한 사양에 설명 합니다.  
  
 [멀티 바이트 문자 집합 (MBCS)에 대 한 지원](../text/support-for-multibyte-character-sets-mbcss.md)  
 일본어 및 중국어 싱글바이트로 표현할 수 없는 같이 문자 집합을 지원에 대 한 유니코드 대신 MBCS를 설명 합니다.  
  
 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)  
 여러 데이터 형식, 루틴 및 다른 개체에 대 한 Microsoft 특정 일반 텍스트 매핑을 제공합니다.  
  
 [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)  
 다양 한 Visual c + + 문자열 형식을 다른 문자열로 변환 하는 방법에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [국제화](../c-runtime-library/internationalization.md)  
 C 런타임 라이브러리의 다국어 기능 지원에 설명 합니다.  
  
 [국가별 샘플](http://msdn.microsoft.com/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Visual c + +에서 국제화를 보여 주는 예제에 대 한 링크를 제공 합니다.  
  
 [언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 C 런타임 라이브러리의 언어 및 국가/지역 문자열을 제공합니다.